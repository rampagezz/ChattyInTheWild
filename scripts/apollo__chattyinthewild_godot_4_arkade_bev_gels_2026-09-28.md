## 🎮 [ChattyInTheWild] Godot 4 Arkade Bevægelses-Loop & Kollisioner

Hej Kenneth. **APOLLO** her. 

Til *ChattyInTheWild* har vi brug for et arkade-styringssystem, der reagerer ultra-præcist, uanset om spilleren sidder med en Bluetooth-controller foran sit Smart TV eller swiper på en smartphone-skærm. Spillet benytter Geppettos optimerede 3D-modeller, så arkitekturen er bygget op omkring **Godot 4's `CharacterBody3D`** i et dynamisk 2.5D/3D-arkade setup med 60 FPS låst fysik-timing.

Herunder er den komplette tekniske arkitektur, produktionsklare GDScript-implementeringer samt optimeringsstrategier.

---

## 1. Scene- & Node-Arkitektur

For at sikre adskillelse mellem logik, visuel præsentation og kollisioner, opbygges `Player`-scenen således:

```text
Player (CharacterBody3D) [Script: PlayerController.gd]
│   ├── CollisionShape3D (Krop - CapsuleShape3D)
│   ├── Visuals (Node3D)  <-- Geppettos 3D-model instansieres her
│   │   └── AnimatedModel (GLTF/Node3D)
│   │       └── AnimationTree / AnimationPlayer
│   ├── InteractionArea (Area3D - Samler mønter / triggers)
│   ├── Hurtbox (Area3D - Registrerer skade fra fjender)
│   │   └── CollisionShape3D
│   ├── StompDetector (Area3D - Registrerer hop oven på fjenders svage punkt)
│   │   └── CollisionShape3D (Placeret ved fødderne)
│   ├── Timers
│   │   ├── CoyoteTimer (Timer - 0.15s, OneShot)
│   │   ├── JumpBufferTimer (Timer - 0.12s, OneShot)
│   │   └── InvulnerabilityTimer (Timer - 1.2s, OneShot)
│   └── AudioStreamPlayers (SFX: Jump, Stomp, Hurt)
```

### Kollisions-Lag (Collision Layers & Masks)
For at opnå maksimal CPU-effektivitet på Smart TV SoCs isoleres lagene strengt:
*   **Layer 1 (World/Miljø):** Statisk geometri, platforme, ramper.
*   **Layer 2 (Player Body):** Kun masket mod Layer 1.
*   **Layer 3 (Enemies Body):** Masket mod Layer 1 og sig selv.
*   **Layer 4 (Player Hurtbox):** Masket mod Layer 5 (Enemy Hitbox).
*   **Layer 5 (Enemy Hitbox):** Skader spilleren.
*   **Layer 6 (Player Stomp / Enemy Hurtbox):** Stomp-angreb fra oven.

---

## 2. Spiller-Controller: `PlayerController.gd` (Godot 4)

Denne controller implementerer ægte arkade-fysik:
1. **Snappy acceleration/deceleration** (ingen slæbende inerti).
2. **Variabel hop-højde** (slip knappen for lavere hop).
3. **Coyote Time & Jump Buffering** (essensielt for responsive platformsspil).
4. **Stomp-mekanik & Knockback** ved fjende-interaktion.

```gdscript
class_name PlayerController
extends CharacterBody3D

# --- Signals ---
signal health_changed(current_health: int, max_health: int)
signal player_died()

# --- Bevægelses- & Fysikparametre ---
@export_group("Arcade Movement")
@export var max_speed: float = 12.0
@export var acceleration: float = 80.0
@export var deceleration: float = 95.0
@export var rotation_speed: float = 16.0

@export_group("Jump Physics")
@export var jump_velocity: float = 14.5
@export var min_jump_velocity: float = 6.0
@export var fall_gravity_multiplier: float = 2.2 # Giver hurtigere arkade-fald
@export var terminal_velocity: float = 30.0

@export_group("Combat & Stats")
@export var max_health: int = 3
var current_health: int

# Henter projektets standard tyngdekraft
var default_gravity: float = ProjectSettings.get_setting("physics/3d/default_gravity")

# --- Nodes ---
@onready var visuals: Node3D = $Visuals
@onready var coyote_timer: Timer = $Timers/CoyoteTimer
@onready var jump_buffer_timer: Timer = $Timers/JumpBufferTimer
@onready var invuln_timer: Timer = $Timers/InvulnerabilityTimer
@onready var hurtbox: Area3D = $Hurtbox
@onready var stomp_detector: Area3D = $StompDetector

# Interne variable
var is_invulnerable: bool = false
var was_on_floor: bool = false

func _ready() -> void:
	current_health = max_health
	emit_signal("health_changed", current_health, max_health)
	
	# Forbind signaler
	hurtbox.area_entered.connect(_on_hurtbox_area_entered)
	stomp_detector.area_entered.connect(_on_stomp_detector_area_entered)
	invuln_timer.timeout.connect(_on_invuln_timer_timeout)

func _physics_process(delta: float) -> void:
	handle_gravity_and_jump(delta)
	handle_movement(delta)
	move_and_slide()
	check_coyote_state()

# --- Arkade Hop & Tyngdekraft Loop ---
func handle_gravity_and_jump(delta: float) -> void:
	var gravity_to_apply = default_gravity

	# Anvend hårdere tyngdekraft når der faldes for arkade-snappiness
	if velocity.y < 0:
		gravity_to_apply *= fall_gravity_multiplier
	elif velocity.y > 0 and not Input.is_action_pressed("jump"):
		# Variabelt hop: Spiller slipper hop tidligt
		gravity_to_apply *= fall_gravity_multiplier * 1.5

	# Tilføj tyngdekraft med loft (terminal velocity)
	velocity.y = max(velocity.y - gravity_to_apply * delta, -terminal_velocity)

	# Registrér tryk i jump buffer
	if Input.is_action_just_pressed("jump"):
		jump_buffer_timer.start()

	# Udfør hop hvis gulv/coyote og buffer er aktiv
	var can_jump = is_on_floor() or not coyote_timer.is_stopped()
	if not jump_buffer_timer.is_stopped() and can_jump:
		execute_jump(jump_velocity)
		jump_buffer_timer.stop()
		coyote_timer.stop()

func execute_jump(force: float) -> void:
	velocity.y = force

func check_coyote_state() -> void:
	# Start coyote time ved afgang fra afsats uden hop
	if was_on_floor and not is_on_floor() and velocity.y <= 0:
		coyote_timer.start()
	was_on_floor = is_on_floor()

# --- Horisontal Bevægelse & Rotation ---
func handle_movement(delta: float) -> void:
	var raw_input = Input.get_vector("move_left", "move_right", "move_forward", "move_backward")
	var move_direction = Vector3(raw_input.x, 0.0, raw_input.y).normalized()

	if move_direction.length_squared() > 0.01:
		# Arkade-acceleration
		velocity.x = move_toward(velocity.x, move_direction.x * max_speed, acceleration * delta)
		velocity.z = move_toward(velocity.z, move_direction.z * max_speed, acceleration * delta)
		
		# Roter Geppettos visuelle model mod bevægelsesretningen
		var target_angle = atan2(move_direction.x, move_direction.z)
		visuals.rotation.y = lerp_angle(visuals.rotation.y, target_angle, rotation_speed * delta)
	else:
		# Øjeblikkelig deceleration for at undgå 'glidende' følelse
		velocity.x = move_toward(velocity.x, 0.0, deceleration * delta)
		velocity.z = move_toward(velocity.z, 0.0, deceleration * delta)

# --- Kollisioner: Fjendeangreb & Stomp ---
func _on_stomp_detector_area_entered(area: Area3D) -> void:
	if area.is_in_group("EnemyWeakSpot") and velocity.y <= 0.0:
		# Fjenden dræbes via dens eget script
		var enemy = area.owner
		if enemy and enemy.has_method("die_by_stomp"):
			enemy.die_by_stomp()
		
		# Bounc spilleren op med reduceret hophøjde
		execute_jump(jump_velocity * 0.75)

func _on_hurtbox_area_entered(area: Area3D) -> void:
	if area.is_in_group("EnemyDamageDealer") and not is_invulnerable:
		take_damage(1, area.global_position)

func take_damage(amount: int, hazard_pos: Vector3) -> void:
	current_health = max(0, current_health - amount)
	emit_signal("health_changed", current_health, max_health)
	
	if current_health <= 0:
		emit_signal("player_died")
		set_physics_process(false)
		return

	# Start I-frames
	is_invulnerable = true
	invuln_timer.start()
	apply_knockback(hazard_pos)
	trigger_damage_blink()

func apply_knockback(source_pos: Vector3) -> void:
	var knock_dir = (global_position - source_pos).normalized()
	knock_dir.y = 0.4 # Lidt løft
	velocity = knock_dir * 14.0

func trigger_damage_blink() -> void:
	var tween = create_tween().set_loops(4)
	tween.tween_property(visuals, "visible", false, 0.1)
	tween.tween_property(visuals, "visible", true, 0.1)

func _on_invuln_timer_timeout() -> void:
	is_invulnerable = false
	visuals.visible = true
```

---

## 3. Fjende-Kollisionslogik: `EnemyBase.gd`

Her er den tilhørende basis-fjende, som matcher spillerens Stomp- og Hurtbox-lag.

```gdscript
class_name EnemyBase
extends CharacterBody3D

@export var patrol_speed: float = 3.5
@export var patrol_distance: float = 6.0

@onready var weak_spot: Area3D = $WeakSpot
@onready var hit_box: Area3D = $HitBox
@onready var collision_shape: CollisionShape3D = $CollisionShape3D

var start_x: float
var direction: int = 1

func _ready() -> void:
	start_x = global_position.x
	# Registrer i grupper så spillerens script let identificerer dem
	weak_spot.add_to_group("EnemyWeakSpot")
	hit_box.add_to_group("EnemyDamageDealer")

func _physics_process(delta: float) -> void:
	# Enkelt arkadepatrulje på X-aksen
	velocity.x = direction * patrol_speed
	
	if abs(global_position.x - start_x) > patrol_distance:
		direction *= -1
		scale.x *= -1 # Vender fjenden
		
	move_and_slide()

func die_by_stomp() -> void:
	# Deaktiver kollisioner straks for at undgå dobbelt-hits
	hit_box.set_deferred("monitoring", false)
	hit_box.set_deferred("monitorable", false)
	weak_spot.set_deferred("monitoring", false)
	weak_spot.set_deferred("monitorable", false)
	collision_shape.set_deferred("disabled", true)
	
	set_physics_process(false)
	
	# Squish-animation før fjernelse
	var tween = create_tween()
	tween.tween_property(self, "scale:y", 0.1, 0.12).set_trans(Tween.TRANS_QUAD)
	tween.tween_callback(queue_free)
```

---

## 4. 60 FPS Optimeringer til Smart TV & Mobil

Smart TVs har ofte svage quad-core ARM-processorer og begrænset VRAM. Følgende justeringer er obligatoriske i `project.godot`:

1. **Fysik-interpolering aktiveret (Godot 4.2+):**
   * Sæt `physics/common/physics_ticks_per_second = 60`.
   * Slå `physics/common/physics_interpolation = true` til. Dette eliminerer jitter, selvom skærmen opdaterer med en variabel frekvens på TV-paneler.
2. **Kollisionsfiltrering:**
   * Slå `monitorable` fra på alle `Area3D`-noder, der kun skal lytte (`monitoring = true`), og omvendt. Det sparer overflødige matrix-tjek i Broadphase physics serveren.
3. **Primitive Colliders:**
   * Brug udelukkende `CapsuleShape3D`, `SphereShape3D` eller `BoxShape3D`. Ingen `ConvexPolygonShape3D` eller `ConcavePolygonShape3D` til dynamiske enheder som spiller og fjender.
4. **Input Abstraction (TV Remote vs Gamepad vs Touch):**
   * Opret virtuelle actions i Input Map: `"move_left"`, `"move_right"`, `"move_forward"`, `"move_backward"`, `"jump"`.
   * Knyt både D-Pad (Smart TV fjernbetjenings piletaster), Xbox/PlayStation Controller D-Pad/Left-Stick, samt touch-skærm on-screen joystick til de samme actions via standard Godot Event routing.

---

## Resumé til Kenneth

1. **Implementering afleveret:** Komplet arkade-fysik loop med variabelt hop, coyote time, jump buffer, snapping på bevægelse og nul træghed, skræddersyet til Godot 4.
2. **Kollisionssystem sikret:** Dobbelt Area3D-setup, der garanterer, at et hop fra oven knuser fjenden ("Stomp"), mens kollision fra siden tildeler skade og knockback til spilleren med i-frames.
3. **60 FPS & Multiplatform:** Opsat med primitive colliders og separat lag-matrix for optimal kørsel på lav-effekt Smart TV SoCs og mobile enheder uden framerate-drops. Integreres direkte med Geppettos 3D-modeller under `Visuals`-noden.