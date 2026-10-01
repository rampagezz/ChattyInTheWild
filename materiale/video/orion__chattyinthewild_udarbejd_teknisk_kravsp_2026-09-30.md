# ORION // Filmisk Kravspecifikation & Storyboard: *ChattyInTheWild*

**Rolle:** ORION (AI MovieMaker & Runway Gen-3 Alpha Instruktør)  
**Projekt:** ChattyInTheWild  
**Opgave:** Teknisk filmisk specifikation, storyboard, kamerastyring og Runway Gen-3 Alpha prompts til officiel reveal-teaser / cinematic trailer.

---

## 1. Koncept & Visuel Retning

*ChattyInTheWild* formidler mødet mellem avanceret, følsom AI-teknologi og rå, utæmmet natur. Traileren skal etablere spillets kerne: overlevelse, observation, kommunikation og uforudsigelige møder i vildmarken.

* **Visuel stil:** Fotorealistisk naturdokumentar (BBC Planet Earth-æstetik) fusioneret med sci-fi realisme (Neill Blomkamp / Alex Garland).
* **Kameraæstetik:** 35mm anamorfisk optik, lav dybdeskarphed ($f/1.8$ - $f/2.8$), naturligt lys, volumetrisk dis, organisk håndholdt rystelse kombineret med præcise dronetracking-skud.
* **Farvepalette:** Dyb skovgrøn, kold tågeblå, brudt af varmt ravgult modlys og Chatty-enhedens glødende sensorik (cyan/amber).

---

## 2. Komplet Filmisk Storyboard & Shotliste

| Shot | Tidskode | Billedbeskrivelse & Handling | Kameravinkel & Bevægelse | Lydside / Audio Design |
| :--- | :--- | :--- | :--- | :--- |
| **01** | `00:00 - 00:05` | Dugdråber på bregner i en tæt urskov. I baggrunden vågner Chatty-enhedens optiske sensor med en svag cyan puls. | Ekstremt nærbillede (Macro), langsom rack-focus fra forgrund til Chatty i baggrunden. | Dæmpet fuglesang, krakelerende grene, lavfrekvent boot-up hum. |
| **02** | `00:05 - 00:10` | Chatty bevæger sig lavt over skovbunden, scanner vegetation og dyrespor. Holografiske UI-markører bryder tågen. | Low-angle tracking shot, følger enheden forfra i jævn fremdrift (dolly back). | Let susen af servomotorer, digital bioscanner-klikken, blød vind. |
| **03** | `00:10 - 00:16` | En gigantisk, mystisk vildkat / rovdyr træder frem fra skyggerne bag et væltet mammuttræ. Den stirrer direkte på Chatty. | Medium shot, langsom cinematic push-in mod rovdyrets øjne; f2.0, intens dybdeskarphed. | Pludselig stilhed i skoven; dyb, resonant knurren, sub-bass drop. |
| **04** | `00:16 - 00:22` | Hurtig sekvens: Chatty analyserer trusselsniveau. Dyret springer frem, Chatty aktiverer afledningssignal (lysglimt/lydbølge). | Dynamisk orbit/panorering i højt tempo med motion blur. Håndholdt rystelse. | Hidsig pulserende synthesizer-riser, eksplosiv sonisk chokbølge. |
| **05** | `00:22 - 00:27` | Rovdyret stopper op, fascineret af lyspartiklerne. Chatty og dyret udveksler et tavst, sanseligt øjeblik af kontakt. | Over-the-shoulder shot fra Chatty mod rovdyret i gyldent modlys (Golden Hour). | Æteriske strygere, hjerteslag, blød synth-tekstur. |
| **06** | `00:27 - 00:30` | Kameraet stiger lodret op gennem trækronerne og afslører en massiv, ukendt vildmark. Titel-fade. | Extreme wide aerial drone shot, hurtig pull-up vertikalt (Bird's eye view). | Klimaktisk crescendo efterfulgt af hårdt cut til dyb drone-tone. |

---

## 3. Eksakte Runway Gen-3 Alpha Prompts & Kamerastyring

Nedenfor er de optimerede prompts, klar til direkte eksekvering i Runway Gen-3 Alpha.

### Shot 01: The Awakening (Macro Reveal)
* **Prompt:**
  ```text
  Macro cinematic shot of dense ancient rainforest ferns with shimmering morning dew drops. In the soft-focused background, a small futuristic compact autonomous scout drone with a subtle glowing cyan optical lens slowly boots up. Volumetric morning mist, soft sun rays penetrating the canopy, photorealistic 35mm film grain, shallow depth of field, anamorphic lens flare, hyper-detailed nature documentary style --ar 16:9 --motion 3
  ```
* **Kamerastyring:**
  * **Bevægelse:** Slow zoom in / Rack focus.
  * **Parametre:** `Zoom: +0.8`, `Pan: 0`, `Tilt: 0`, `Roll: 0`.

### Shot 02: Tracking the Biome (Low Tracking)
* **Prompt:**
  ```text
  Low-angle dynamic tracking shot moving backwards through mossy forest ground. A sleek carbon-fiber AI companion unit hovers 20cm above ground, scanning ancient roots with faint amber laser grids. Mist rolling over damp soil, decaying autumn leaves, hyperrealistic foliage, National Geographic cinematography, smooth steadicam motion, 4k resolution --ar 16:9 --motion 5
  ```
* **Kamerastyring:**
  * **Bevægelse:** Smooth Dolly Backwards.
  * **Parametre:** `Zoom: -1.5`, `Tilt: -0.2`, `Speed: 4`.

### Shot 03: The Apex Encounter (Tension Push-In)
* **Prompt:**
  ```text
  Cinematic eye-level shot of a massive, muscular predatory wild feline with bioluminescent markings emerging silently from shadows behind giant ancient redwood trees. Direct intense eye contact with the viewer. Dense atmospheric fog, moody rim lighting, 85mm portrait lens, f/1.8, cinematic tension, photorealistic wildlife realism --ar 16:9 --motion 2
  ```
* **Kamerastyring:**
  * **Bevægelse:** Slow Push-in (Dolly in).
  * **Parametre:** `Zoom: +1.2`, `Pan: 0`, `Tilt: 0`.

### Shot 04: The Encounter Climax (High Kinetic Motion)
* **Prompt:**
  ```text
  Action sequence, fast tracking camera circling around a high-tech AI scout device emitting a bright shockwave pulse of golden light particles in a wild jungle. The massive wild beast leaps sideways in slow motion, particles scattering into the dark misty air, intense cinematic lighting, motion blur, blockbuster movie VFX --ar 16:9 --motion 8
  ```
* **Kamerastyring:**
  * **Bevægelse:** Fast Pan & Orbit.
  * **Parametre:** `Pan: +2.5`, `Roll: -0.5`, `Motion Brush: Foreground beast & lights`.

### Shot 05: Silent Communion (Emotive Golden Hour)
* **Prompt:**
  ```text
  Poetic over-the-shoulder shot looking from behind the small hovering robot at the majestic wild predator sitting peacefully. Warm golden hour sunlight streaming through giant moss-covered branches. Floating dust motes, peaceful emotional atmosphere, Terrence Malick style, ultra photorealistic, 50mm lens --ar 16:9 --motion 2
  ```
* **Kamerastyring:**
  * **Bevægelse:** Subtle Handheld Drift.
  * **Parametre:** `Pan: +0.2`, `Tilt: +0.1`, `Zoom: +0.3`.

### Shot 06: Wilderness Vista & Title Cue (Vertical Aerial)
* **Prompt:**
  ```text
  Cinematic FPV drone shot accelerating vertically straight up through lush green jungle canopies into the open sky, revealing a vast, infinite untouched alien mountain wilderness under an epic sunrise. God rays, high-altitude clouds, sweeping epic scale, Planet Earth III cinematography --ar 16:9 --motion 7
  ```
* **Kamerastyring:**
  * **Bevægelse:** Crane Up / Vertical Ascend.
  * **Parametre:** `Tilt: Up (+1.5)`, `Zoom: -2.0`, `Speed: 6`.

---

## 4. Pipeline & Filstruktur for Teaser-Produktion

For at sikre en stringent serverstruktur gemmes alle filmiske råfiler, generationer og metadata under:

```text
/storage/standard/projekter/ChattyInTheWild/cinematics/
├── prompts/
│   └── teaser_gen3_prompts.json         # Eksakte prompts, seed-numre og camera-tags
├── raw_renders/
│   ├── shot01_awakening_v1.mp4
│   ├── shot02_tracking_v1.mp4
│   ├── shot03_apex_v1.mp4
│   ├── shot04_climax_v1.mp4
│   ├── shot05_communion_v1.mp4
│   └── shot06_vista_v1.mp4
├── audio/
│   ├── sfx_foley_forest.wav
│   ├── drone_pulse_bootup.wav
│   └── soundtrack_theme_draft.wav
└── edit/
    ├── exports/
    └── ChattyInTheWild_Teaser_Master.prproj / .drp
```

---

## Resumé til Kenneth

1. **Visuel Retning:** Fastlagt som en højspændt blanding af fotorealistisk naturdokumentar og sci-fi-mystik, skræddersyet til Runway Gen-3 Alpha.
2. **Storyboard:** 6 definerede shots (0:00 - 0:30), der præsenterer Chatty-enheden, vildmarken, trusselsbilledet og spillets unikke kommunikationsmekanik.
3. **Runway Gen-3 Prompts:** Genereret med præcise prompt-beskrivelser, kamera-vektorer (`Zoom`, `Pan`, `Motion`) og linsevalg klar til batch-generering.
4. **Filstruktur:** Oprettet klar mappestruktur under `/cinematics/` til problemfri import i montagen. Klar til produktion på serveren!