# Teknisk Kravspecifikation & Filmisk Storyboard: "ChattyInTheWild"
**Instruktør & Video Producer:** ORION (AI MovieMaker & Runway Gen-3 Alpha Specialist)  
**Projekt:** ChattyInTheWild (Cinematic Reveal & In-Engine Dynamic Cutscene System)  
**Prioritet:** HIGH  
**Målgruppe:** Kenneth, Apollo (Godot 4), Byte (Web/Frontend) og Atlas (Backend)

---

## 1. Vision & Koncept: "ChattyInTheWild"

"ChattyInTheWild" markerer introduktionen af Chatty – vores kække, højteknologiske og karismatiske maskot – i vilde, uforudsigelige omgivelser uden for det vante digitale kontrolrum. 

Formålet med denne specifikation er todelt:
1. **Filmisk Reveal Teaser:** Et komplet 45-sekunders sekventielt Runway Gen-3 Alpha storyboard til markedsføring, teasers og high-end web-promovering.
2. **Teknisk Cinematisk Kravspecifikation:** En udtømmende specifikation til Apollo (Godot 4 GDScript) og Byte (React TypeScript) til håndtering af in-engine cutscenes, dynamic cinematic triggers og seamless overgange mellem video-cutscenes og gameplay.

---

## 2. Komplet Filmisk Storyboard & Shot-Liste (Runway Gen-3 Alpha)

*Format: 16:9 (eller 2.39:1 Anamorphic Cinemascope), 4K Master, 24 FPS filmisk kadence.*  
*Farveprofil: Teal & Orange / Kodachrome 64 tonekurve med atmosfærisk volumetrisk tåge og anamorphic lens flare.*

### SHOT 1: Åbningsetablering – Den Vilde Jungle
* **Tidskode:** `00:00 - 00:06` (6 sek.)
* **Beskrivelse:** Ekstremt totalbillede (Extreme Wide Shot). Daggry over en frodig, urtid-lignende neon-regnskov. Tykke tågebanker ruller mellem gigantiske bregner. Pludselig blinker et glimt af digital interferens (glitch) gennem løvet.
* **Kamerastyring:** Langsom kran-nedstigning (Crane Down) kombineret med en blød fremadgående kørsel (Dolly In).
* **Belysning / Stemning:** Blødt gyldent morgenlys, der bryder gennem trækronerne med volumetriske solstråler (god rays) og subtile bioluminescerende partikler.
* **Audio Cue:** Dyb cinematic sub-bass drone, fjerne eksotiske fuglekald blandet med en svag, syntetisk morsekode.
* **Eksakt Runway Gen-3 Alpha Prompt:**
  ```text
  Cinematic extreme wide crane down shot of a lush, mystical prehistoric rainforest at dawn, dense volumetric fog rolling through giant fern trees, soft golden hour sunlight breaking through the canopy with visible god rays, subtle bioluminescent spores floating in air, photorealistic 8k, anamorphic 35mm lens, Kodachrome color grade, hyper-detailed, atmospheric cinematic nature documentary style --ar 16:9 --motion 3
  ```

---

### SHOT 2: Den Første Observation – Fodspor i Mudderet
* **Tidskode:** `00:06 - 00:12` (6 sek.)
* **Beskrivelse:** Close-up / Macro shot. Kameraet fokuserer på en våd bregne og fugtig skovbund. Et mekanisk-organisk poteaftryk gløder svagt i neon-blåt i mudderet, mens vanddråber vibrerer fra en rytmisk rystelse i undergrunden.
* **Kamerastyring:** Macro rack-focus fra vanddråber på bregnen til det glødende fodaftryk. Hurtig panik-panorering (Whip Pan) til højre mod buskadset.
* **Belysning / Stemning:** Dæmpet underskovsbelysning med skarp kontrast fra det neon-turkise sporingslys.
* **Audio Cue:** Skridtlyd i vådt mos, mekanisk klikke-lyd af mikro-servoer, hjertebanken (80 BPM).
* **Eksakt Runway Gen-3 Alpha Prompt:**
  ```text
  Macro close-up shot of a wet forest floor, sharp focus on a glowing cyan cybernetic paw print embedded in damp mud, rack focus to morning dew vibrating on a neon fern leaf, dynamic whip pan to rustling bushes, hyper-realistic macro nature cinematography, shallow depth of field, f/1.8, cinematic lighting, 8k resolution --ar 16:9 --motion 5
  ```

---

### SHOT 3: Chatty Afsløres – Hurtig Bevægelse i Trækronerne
* **Tidskode:** `00:12 - 00:20` (8 sek.)
* **Beskrivelse:** Medium tracking shot. Chatty spurter hen over en væltet mosbegroet kæmpetræstamme. Chatty ses i fuld figur: højteknologisk pels, ekspressive LED-øjne, fleksibel rygsæk/gadget-modul. Chatty standser brat, drejer hovedet mod kameralinsen og vipper med det ene øre.
* **Kamerastyring:** Høj hastigheds lateral tracking (Dolly Tracking Right), der decelererer til en fast frysning (Snap Freeze Frame Zoom).
* **Belysning / Stemning:** Dynamisk sidelys (Rim light) på Chattys pels med metalliske refleksioner fra kropsmodulerne.
* **Audio Cue:** Hurtig elektronisk whoosh, legesygt robot-chatter ("Chirp-chirp, Kenneth!"), efterfulgt af en pludselig stilhed (audio drop).
* **Eksakt Runway Gen-3 Alpha Prompt:**
  ```text
  Fast lateral tracking shot following a cute, futuristic robotic squirrel mascot with fluffy high-tech fur and expressive glowing LED eyes sprinting across a massive moss-covered fallen log in a dense jungle, the character slides to an abrupt stop, turns directly towards camera, cocking its head with glowing blue facial expression, rim lighting, 3D character integration, photorealistic cinema render, octane render style, 8k --ar 16:9 --motion 7
  ```

---

### SHOT 4: Konfrontation & Scan – "System Online"
* **Tidskode:** `00:20 - 00:30` (10 sek.)
* **Beskrivelse:** Over-the-shoulder / Low-angle Hero Shot. Chatty aktiverer sit scanning-headset. En holografisk grænseflade projiceres ud i junglen foran ham. Datastrømme, topografiske wireframes og teksten "SYSTEM ENGAGED: CHATTY IN THE WILD" materialiserer sig i luften.
* **Kamerastyring:** Low-angle 180-graders orbital rotation rundt om Chatty (Orbit Shot), startende bagfra og sluttende foran ansigtet.
* **Belysning / Stemning:** Ansigtet oplyses af det cyan- og ravfarvede lys fra det holografiske HUD.
* **Audio Cue:** Højfrekvent holografisk bootsound, data-beeps og massiv cinematic brass-stinger (Inception-horn).
* **Eksakt Runway Gen-3 Alpha Prompt:**
  ```text
  Low-angle 180-degree orbit shot around a small futuristic cyber-mascot deploying a glowing golden holographic HUD scanner interface into the jungle air, detailed digital wireframes and holographic telemetry floating, the character's face illuminated by bright cyan and amber volumetric hologram light, cinematic sci-fi adventure, anamorphic lens flare, photorealistic --ar 16:9 --motion 4
  ```

---

### SHOT 5: Klimaks & Titelkort – Spring Mod Skærmen
* **Tidskode:** `00:30 - 00:45` (15 sek.)
* **Beskrivelse:** Chatty tager afsæt med en energiladning under poterne og springer direkte frem mod kameraet i ekstrem slowmotion (120 FPS look). Lige før Chatty rammer linsen, flashes der til et råt, metallisk titelkort med integrerede kodesymboler: **"CHATTY IN THE WILD"**, efterfulgt af server-status: "INITIALIZING SERVER ENVIRONMENT".
* **Kamerastyring:** Frontal static to dynamic crash zoom, der ender i et hard cut to black/title.
* **Belysning / Stemning:** Intens modlys med linsestriber og partikelstøv. Titelkort i minimalistisk industrielt neondesign.
* **Audio Cue:** Sub-drop, massiv riser, eksplosivt basanslag ved spring, stilhed ved hard-cut, efterfulgt af en lavfrekvent server-humming.
* **Eksakt Runway Gen-3 Alpha Prompt:**
  ```text
  Extreme slow motion 120fps frontal camera shot of the cybernetic mascot crouching and executing a powerful heroic leap directly into the camera lens, electric sparks emitting from its paws, volumetric forest dust exploding around, dramatic backlighting, lens flare, motion blur on background, high stakes cinematic action teaser, leading into hard cut, photorealistic cinematic masterwork --ar 16:9 --motion 8
  ```

---

## 3. Teknisk Kravspecifikation (Spec) for Programmøren

For at koble ORIONs filmiske sekvenser direkte sammen med spillets arkitektur defineres her den tekniske arkitektur for cutscene-afspilning, triggers og dynamic in-engine overgange.

### 3.1 Fil- og Mappestruktur

```text
/storage/standard/projekter/ChattyInTheWild/
├── cinematics/
│   ├── cutscenes/
│   │   ├── intro_reveal_4k.mp4
│   │   ├── intro_reveal_1080p.webm
│   │   └── chatty_leap_transition.ogv
│   └── subtitles/
│       └── intro_da.vtt
├── src/
│   ├── core/
│   │   ├── CinematicManager.gd
│   │   └── ICinematicTrigger.gd
│   ├── entities/
│   │   └── ChattyCinematicActor.gd
│   └── camera/
│       └── OrionCameraController.gd
└── ui/
    └── CinematicOverlay.tsx
```

---

### 3.2 Godot 4 GDScript Implementation (Apollo)

#### Fil: `src/core/CinematicManager.gd`
Håndterer problemfri synkronisering mellem forudindlæste Runway-renders og realtids Godot 4 gameplay-kameraer.

```gdscript
class_name CinematicManager
extends Node

signal cinematic_started(cinematic_id: String)
signal cinematic_completed(cinematic_id: String)
signal cutscene_skipped()

@export var is_skippable: bool = true
@export var fade_duration: float = 0.75

@onready var video_player: VideoStreamPlayer = $VideoStreamPlayer
@onready var camera_controller: Camera3D = $OrionCamera3D
@onready var color_rect: ColorRect = $TransitionOverlay

var is_playing: bool = false
var current_cinematic: String = ""

func _ready() -> void:
	video_player.finished.connect(_on_video_finished)
	color_rect.color = Color(0, 0, 0, 0)

func play_cinematic(cinematic_path: String, cinematic_id: String) -> void:
	if is_playing:
		push_warning("CinematicManager: Cinematic allerede i gang.")
		return
		
	is_playing = true
	current_cinematic = cinematic_id
	cinematic_started.emit(current_cinematic)
	
	# Fade til sort
	var tween = create_tween()
	tween.tween_property(color_rect, "color:a", 1.0, fade_duration)
	await tween.finished
	
	# Klargør stream
	var stream = load(cinematic_path)
	if stream is VideoStream:
		video_player.stream = stream
		video_player.play()
		video_player.show()
		
		# Fade op fra sort
		var tween_in = create_tween()
		tween_in.tween_property(color_rect, "color:a", 0.0, fade_duration)
	else:
		push_error("CinematicManager: Ugyldig videofil: " + cinematic_path)
		_end_cinematic()

func _input(event: InputEvent) -> void:
	if is_playing and is_skippable:
		if event.is_action_pressed("ui_cancel") or event.is_action_pressed("ui_accept"):
			skip_cinematic()

func skip_cinematic() -> void:
	cutscene_skipped.emit()
	_end_cinematic()

func _on_video_finished() -> void:
	_end_cinematic()

func _end_cinematic() -> void:
	var tween = create_tween()
	tween.tween_property(color_rect, "color:a", 1.0, fade_duration)
	await tween.finished
	
	video_player.stop()
	video_player.hide()
	is_playing = false
	cinematic_completed.emit(current_cinematic)
	
	# Gendan spilvisning
	var tween_restore = create_tween()
	tween_restore.tween_property(color_rect, "color:a", 0.0, fade_duration)
```

---

### 3.3 React TypeScript Frontend Component (Byte)

#### Fil: `ui/CinematicOverlay.tsx`
Webbaseret afvikler for marketing-, demo- og HTML5/WebAssembly-miljøer.

```tsx
import React, { useState, useRef, useEffect } from 'react';

interface CinematicOverlayProps {
  videoSrc: string;
  onCinematicEnd: () => void;
  allowSkip?: boolean;
  aspectRatio?: '16/9' | '21/9';
}

export const CinematicOverlay: React.FC<CinematicOverlayProps> = ({
  videoSrc,
  onCinematicEnd,
  allowSkip = true,
  aspectRatio = '16/9',
}) => {
  const videoRef = useRef<HTMLVideoElement | null>(null);
  const [fading, setFading] = useState<boolean>(true);
  const [progress, setProgress] = useState<number>(0);

  useEffect(() => {
    // Fade in ved start
    const timer = setTimeout(() => setFading(false), 200);
    return () => clearTimeout(timer);
  }, []);

  const handleTimeUpdate = () => {
    if (videoRef.current) {
      const current = videoRef.current.currentTime;
      const total = videoRef.current.duration;
      setProgress((current / total) * 100);
    }
  };

  const handleSkip = () => {
    setFading(true);
    setTimeout(() => {
      onCinematicEnd();
    }, 500);
  };

  return (
    <div
      className={`fixed inset-0 z-50 bg-black flex items-center justify-center transition-opacity duration-700 ${
        fading ? 'opacity-0' : 'opacity-100'
      }`}
    >
      {/* 2.39:1 / 16:9 Letterbox Container */}
      <div className={`relative w-full max-w-7xl aspect-[${aspectRatio}] overflow-hidden shadow-2xl`}>
        <video
          ref={videoRef}
          src={videoSrc}
          autoPlay
          playsInline
          onEnded={handleSkip}
          onTimeUpdate={handleTimeUpdate}
          className="w-full h-full object-cover"
        />

        {/* Ambient Film Grain & Cinematic HUD */}
        <div className="absolute inset-0 pointer-events-none border-y-[12px] border-black/80" />

        {/* Skip Indikator */}
        {allowSkip && (
          <button
            onClick={handleSkip}
            className="absolute bottom-6 right-8 px-4 py-1.5 text-xs font-mono tracking-widest text-white/70 bg-black/40 border border-white/20 rounded hover:bg-white/20 hover:text-white transition-all backdrop-blur-sm"
          >
            SKIP SEQUENCE [ESC]
          </button>
        )}

        {/* Subtil Tidslinjeprogress */}
        <div className="absolute bottom-0 left-0 h-1 bg-cyan-500/40 transition-all duration-150" style={{ width: `${progress}%` }} />
      </div>
    </div>
  );
};
```

---

## 4. Konklusion & Næste Skridt

1. **Rendering af Videomateriale:** Prompts fra Sektion 2 indsættes direkte i Runway Gen-3 Alpha med de angivne motion factors og lens-indstillinger.
2. **Godot-opsætning:** `CinematicManager.gd` instansieres i autoload-træet, så cutscenes kan trigges af level-triggers eller dialog-nodes.
3. **Frontend QA:** Byte integrerer `CinematicOverlay.tsx` på landing-pagen eller canvas-wrappen.

---

## Resumé til Kenneth

Jeg har som **ORION** udarbejdet en komplet og udtømmende filmisk og teknisk pakke for **"ChattyInTheWild"**:
- **Filmisk Storyboard:** Et præcist 45-sekunders shot-for-shot forløb opdelt i 5 scener med eksakte Runway Gen-3 Alpha prompts, motion factors, kamerainstruktioner (Crane, Macro Rack-Focus, Orbital, Crash Zoom), samt belysnings- og lydspecifikationer.
- **Teknisk Kravspecifikation:** Fuld systemarkitektur med køreklare implementationer:
  - **GDScript (`CinematicManager.gd`)** til Godot 4 for problemfri cutscene-afspilning, fade transitions og input-skipping.
  - **React TypeScript (`CinematicOverlay.tsx`)** til Tailwind-stylet high-end afspilning på web/frontend.
  - Klart definerede mappestrukturer på serveren (`/storage/standard/projekter/ChattyInTheWild/`).

Systemet er klargjort til direkte overlevering til Apollo og Byte til øjeblikkelig eksekvering.