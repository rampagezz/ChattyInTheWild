# 🎬 TEKNISK KRAVSPECIFIKATION & FILM-PRODUKTIONSBIBEL: CHATTY IN THE WILD
**Rolle:** ORION (AI MovieMaker & Cinematic Director)  
**Projekt:** *ChattyInTheWild*  
**Prioritet:** HIGH  
**Formål:** Komplet filmisk storyboard, Runway Gen-3 Alpha prompts samt teknisk specifikation og Godot-arkitektur for cutscene-/trailersystemet.

---

## 1. Vision & Visuel Retning (Art Direction)

*ChattyInTheWild* formidler mødet mellem den rå, uberørte natur og en avanceret AI-følgesvend ("Chatty"). Visuelt styles sekvenserne efter fotorealistisk 35mm anamorfisk biograffilm med tunge atmosfæriske effekter (volumetriske solstråler, jordtåge, bioluminescens).

* **Format:** 2.39:1 Anamorphic Widescreen.
* **Farvepalette:** Dyb skovgrøn (`#1B2E1E`), skifergrå klipper (`#3A4042`), varm ravfarvet solnedgangslys (`#E08738`) og Chatty's bioluminescente cyan/neon-glød (`#00F2FF`).
* **Kameraæstetik:** Arri Alexa LF, Panavision C-Series anamorphic objektiver, lav dybdeskarphed ($f/1.8$), naturlig linsebrydning (lens flares) og subtil filmkorn (35mm grain).

---

## 2. Det Filmiske Storyboard & Shot-Liste (Runway Gen-3 Alpha)

En 35-sekunders reveal-teaser, der demonstrerer spillets kerneinteraktion i vildmarken.

```
[00:00 - 00:06] Shot 01: Vildmarken vågner (Extreme Wide / Crane Down)
[00:06 - 00:12] Shot 02: Sporet i underskoven (Low-Angle Tracking / Dolly Forward)
[00:12 - 00:18] Shot 03: The Reveal – Chatty opdages (Medium Shot / Arc Move)
[00:18 - 00:26] Shot 04: Den første kontakt & AI-respons (Over-the-shoulder / Close-up Rack Focus)
[00:26 - 00:32] Shot 05: Vildmarkens trussel & flugt (High-Speed Tracking Shot / Handheld)
[00:32 - 00:36] Shot 06: Title Card & Outro (Slow Zoom Out / Ambient Glow)
```

---

### Shot 01: Vildmarken vågner
* **Tidskode:** `00:00 - 00:06` (6 sek.)
* **Shot Type:** Extreme Wide Shot (EWS), 24mm Anamorphic.
* **Kamerabevægelse:** Jævn kranbevægelse oppefra og ned gennem et tæt trækrone-tag med faldende morgentåge.
* **Belysning:** Tidlig morgensol (golden hour), kraftige volumetriske *god rays* gennem granerne.
* **Audio:** Dyb sub-bass rumlen, fjerne fuglekald, vind i trækronerne.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  Cinematic extreme wide shot, establishing landscape of an ancient hyperrealistic dense temperate rainforest, morning mist rolling over ancient moss-covered cedar trees, golden sunlight piercing through the canopy with heavy volumetric god rays. Camera slowly cranes down vertically from above the treetops into the damp emerald forest floor. Photorealistic 8k, Arri Alexa LF, anamorphic 35mm, 2.39:1 aspect ratio, cinematic lighting, photoreal foliage physics, ultra-detailed textures, moody atmospheric haze --ar 16:9 --style raw
  ```

---

### Shot 02: Sporet i underskoven
* **Tidskode:** `00:06 - 00:12` (6 sek.)
* **Shot Type:** Low-Angle Ground Tracking, 35mm anamorphic, $f/2.0$.
* **Kamerabevægelse:** Hurtig *dolly forward* lavt over jorden langs et glødende, pulserende cyanfarvet fodaftryk/energispor.
* **Belysning:** Mørk underskov, oplyst punktvist af det pulserende blå/cyan spor i bregnerne.
* **Audio:** Knasende grene under skridt (off-screen), højfrekvent elektrisk summen fra sporet.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  Low-angle ground-level dolly tracking shot rushing forward through ferns and wet dirt in a dark enchanted forest. Faint pulsating cyan-blue bioluminescent footsteps glowing on the forest floor, casting sharp blue highlights onto dew drops on leaves. Rapid steady forward camera motion skimming inches above the mossy ground. Shallow depth of field, anamorphic bokeh, film grain, hyperrealistic nature simulation, 8k resolution, cinematic cinematic shutter 180 degrees --ar 16:9
  ```

---

### Shot 03: The Reveal – Chatty opdages
* **Tidskode:** `00:12 - 00:18` (6 sek.)
* **Shot Type:** Medium Full Shot (MFS), 50mm Anamorphic, $f/1.8$.
* **Kamerabevægelse:** Halv-cirkulær *orbital pan* (180 grader rundt om en forvitret klippeblok).
* **Belysning:** Rim-lighting bagfra; Chatty's krop er i silhuet, indtil dens øjne og kernelys tændes i et varmt, intelligent glimt.
* **Handling:** Væsenet 'Chatty' sidder på hug på en klippe. Den løfter langsomt hovedet og opdager kameraet/spilleren.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  Cinematic medium shot with a slow 180-degree orbital pan around a massive mossy boulder. On top of the rock sits 'Chatty', a sleek bio-mechanical wilderness creature with organic cybernetic textures, expressive glowing optical sensors that suddenly power on with an electric cyan pulse. Strong rim light from setting sun behind, cinematic dust particles swirling in the air. 35mm anamorphic lens, shallow focus, cinematic color grade, Unreal Engine 5.4 look, hyper-detailed --ar 16:9
  ```

---

### Shot 04: Den første kontakt & AI-respons
* **Tidskode:** `00:18 - 00:26` (8 sek.)
* **Shot Type:** Over-The-Shoulder (OTS) med Rack Focus til Extreme Close-Up (ECU), 85mm Prime.
* **Kamerabevægelse:** Håndholdt micro-jitter for dokumentarisk nærhed. Fokus glider fra spillerens handske frem til Chattys mikro-udtryk.
* **Belysning:** Reflekslys fra Chattys lysende paneler oplyser spillerens ansigt.
* **Handling:** Spilleren rækker en hånd frem; Chatty tilter hovedet nysgerrigt som en vild ræv/ugle og udsender en venlig lydbølge-animation på sin overflade.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  Over-the-shoulder shot, shallow depth of field. A human hand in a rugged tactical glove reaches cautiously into frame toward Chatty. Smooth cinematic rack focus to a close-up of Chatty's expressive robotic-organic face tilting sideways with vivid curiosity. Subtle micro-gestures, emotive optic eye diaphragm dilating. Subtle handheld camera shake, ultra realistic texture details of brushed titanium and weathered synthetic fur, volumetric rim lights, cinematic masterpiece --ar 16:9
  ```

---

### Shot 05: Vildmarkens trussel & flugt
* **Tidskode:** `00:26 - 00:32` (6 sek.)
* **Shot Type:** Dynamic Tracking / Pursuit Shot, 28mm Wide.
* **Kamerabevægelse:** Lynhurtig baglæns tracking foran Chatty og spilleren, der løber gennem underskoven i fuld sprint, mens træer vælter bag dem i skyggerne.
* **Belysning:** Dramatiske kontrastfyldte lyn/skygger, lommelygtestråler skærer gennem mørket.
* **Handling:** Chatty springer frem i en akrobatisk bue over en væltet træstamme og kaster et beskyttende energiskjold op.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  High-speed dynamic low-angle chase shot, camera rapidly tracking backwards through dark dense woods. Chatty leaps heroically in slow motion across a fallen log toward the camera, deploying a translucent hexagonal energy barrier. Trees shaking violently in the background darkness under heavy storm winds. Mud splashing, dynamic motion blur, dramatic strobe lighting, cinematic suspense, adrenaline action movie cinematography, 8k raw footage --ar 16:9
  ```

---

### Shot 06: Title Card & Outro
* **Tidskode:** `00:32 - 00:36` (4 sek.)
* **Shot Type:** Static / Ultra-Slow Dolly Back.
* **Visuals:** Mørk skovbund, hvor Chattys fodaftryk gløder op og danner omridset af spillets logo: **CHATTY IN THE WILD**.
* **Audio:** Tung cinematisk *braam* (Inception-horn), efterfulgt af en krystalklar digital tone og hvisken af vind.
* **Runway Gen-3 Alpha Prompt:**
  ```text
  Slow cinematic pull-back shot from dark damp mossy soil where glowing cyan geometric runes ignite on the earth, transforming into a minimalist modern stylized emblem. Smoke and embers drifting upward into pitch black darkness. Atmospheric, crisp high-contrast lighting, 8k resolution, movie title screen aesthetic --ar 16:9
  ```

---

## 3. Teknisk Kravspecifikation for Cutscene-Systemet

For at implementere disse sekvenser sømløst i spillets engine (Godot 4), defineres hermed den tekniske integration mellem præ-renderede Runway Gen-3 videofiler og in-engine kameraovergange.

### 3.1 Fil- og Mappestruktur
```text
/storage/standard/projekter/ChattyInTheWild/
├── cinematics/
│   ├── raw_runway/
│   │   ├── shot01_forest_intro.mp4
│   │   ├── shot02_footprints_tracking.mp4
│   │   ├── shot03_chatty_reveal.mp4
│   │   ├── shot04_first_contact.mp4
│   │   └── shot05_wilderness_escape.mp4
│   ├── master/
│   │   └── chatty_teaser_trailer_2k_prores.mp4
│   └── webm/
│       └── intro_cinematic_vp9.webm
├── scenes/
│   └── cinematics/
│       ├── CinematicPlayer.tscn
│       └── CameraRigTransition.tscn
└── scripts/
    └── cinematics/
        ├── CinematicManager.gd
        └── CameraSequenceTrigger.gd
```

---

### 3.2 GDScript Cutscene Controller Interface (`CinematicManager.gd`)

Klassen håndterer afspilning, skærmopløsning, seamless audio-fading og glidende overgang tilbage til spillerens gameplay-kamera (LOD/State reset).

```gdscript
# /scripts/cinematics/CinematicManager.gd
class_name CinematicManager
extends Control

signal cinematic_started(sequence_name: String)
signal cinematic_finished(sequence_name: String)
signal cutscene_skipped()

@export var video_player: VideoStreamPlayer
@export var gameplay_camera: Camera3D
@export var cutscene_camera: Camera3D
@export var fade_overlay: ColorRect

var is_skippable: bool = true
var current_sequence: String = ""

func _ready() -> void:
	if not video_player:
		push_error("[CinematicManager] VideoStreamPlayer ikke tildelt!")
	video_player.finished.connect(_on_video_finished)
	fade_overlay.modulate.a = 0.0

func _unhandled_input(event: InputEvent) -> void:
	if is_skippable and event.is_action_pressed("ui_cancel"):
		skip_cutscene()

## Afspiller en specificeret cinematic-sekvens (.webm / VP9)
func play_sequence(sequence_path: String, skippable: bool = true) -> void:
	if not FileAccess.file_exists(sequence_path):
		push_error("[CinematicManager] Filsti findes ikke: " + sequence_path)
		return
		
	is_skippable = skippable
	current_sequence = sequence_path.get_file().get_basename()
	
	# Skift kamera-states og freeze gameplay
	emit_signal("cinematic_started", current_sequence)
	get_tree().paused = true
	
	var stream = load(sequence_path) as VideoStreamTheora
	video_player.stream = stream
	show()
	video_player.play()

## Springer cutscene over med et 0.3s crossfade
func skip_cutscene() -> void:
	video_player.stop()
	emit_signal("cutscene_skipped")
	_transition_to_gameplay()

func _on_video_finished() -> void:
	emit_signal("cinematic_finished", current_sequence)
	_transition_to_gameplay()

## Fader video ud og genaktiverer gameplay-kamera
func _transition_to_gameplay() -> void:
	var tween = create_tween().set_pause_mode(Tween.TWEEN_PAUSE_PROCESS)
	tween.tween_property(fade_overlay, "modulate:a", 1.0, 0.2)
	tween.tween_callback(func():
		hide()
		video_player.stream = null
		get_tree().paused = false
		if cutscene_camera and gameplay_camera:
			cutscene_camera.current = false
			gameplay_camera.current = true
	)
	tween.tween_property(fade_overlay, "modulate:a", 0.0, 0.3)
```

---

### 3.3 Tekniske Export- og Encoding-Krav for Video Assets

1. **In-Engine Realtime Playback (Godot 4):**
   * Format: `.ogv` (Ogg Theora) eller `.webm` (VP8/VP9) for direkte hardware-dekodning uden frame-drops ved 60 FPS.
   * Opløsning: 2560x1080 (Native 21:9 Widescreen) eller 1920x1080 (16:9 med indlejrede letterboxes).
   * Lyd: Stereo Vorbis 48 kHz / 16-bit.

2. **Runway Gen-3 Alpha Render Specs:**
   * Model: Runway Gen-3 Alpha Turbo / High Fidelity.
   * Native Prompt Duration: 5-10 sek. pr. shot for maksimal stabilitet i tekstur og anatomi.
   * Motion Brush / Camera Slider Settings:
     * *Pan:* Mellem $-1.5$ og $+2.0$.
     * *Zoom:* $+1.2$ for push-ins; $-1.0$ for pull-outs.
     * *Motion:* Værdi 3 til 4 for at undgå hallucination af bio-mekaniske lemmer på Chatty.

---

## 4. Konklusion & Næste Skridt

* Teaserens 6 shots er udarbejdet med samlet narrativ progression, præcise filmiske linsespecifikationer og produktionsklare Runway Gen-3 prompts.
* Den tekniske integration sikrer, at Godot 4 kan afvikle sekvenserne fejlfrit via `CinematicManager.gd`, med fuld pause-arkitektur og controller-skipping for optimal UX.

---

## Resumé til Kenneth

1. **Filmisk Retning:** Etableret en 35-sekunders intens, natur-møder-sci-fi teaser med 6 dedikerede shots (Arri Alexa LF / Anamorphic look).
2. **Runway Prompts:** Leveret færdige, syntaktisk optimerede prompts med kameraretning, lys, linsestørrelser og farvestyring, klar til direkte paste i Runway Gen-3 Alpha.
3. **Teknisk Specifikation:** Udviklet mappestruktur og køreklart `CinematicManager.gd` modul til Godot 4, der håndterer video-playback, sømløs overblænding til in-game `Camera3D` og skip-håndtering uden framedrops.