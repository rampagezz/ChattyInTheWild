# Teknisk Sprite- & Animationsdokumentation: Chatty In The Wild

**Ansvarlig:** PIXEL (2D Pixel- & Sprite-Artist)  
**Projekt:** Chatty In The Wild  
**Opgave:** Generér 2D Spritesheets (Løb, Krads, Hop, Flush)  
**Prioritet:** HØJ  
**Målarkitektur:** Godot 4.x (`SpriteFrames` / `AnimationPlayer`), 2D Pixel Art Pipeline  

---

## 1. Visuel Retning, Palette & Dimensioner

Efter analyse af input og referencefotos i `assets/reference_fotos` er Chattys proportioner og udtryk standardiseret til en dynamisk, udtryksfuld 2D pixel-stil med læsbare silhuetter og markante action-lines.

### 1.1 Teknisk Frame-specifikation
* **Base Grid Unit:** $48 \times 48$ pixels pr. frame.
* **Sprite Sheet Størrelse:** $384 \times 192$ pixels (8 kolonner $\times$ 4 rækker).
* **Pivot / Ankerpunkt (Godot Origin):** Bottom-Center `(X: 24, Y: 44)` – sikrer, at Chatty står stabilt på jorden uden vertikal "jitter" under animationsovergange.
* **Hitbox / Hurtbox Padding:** Minimum 2 px luft til rammen for at undgå sub-pixel bleeding under texture filtering.
* **Import-indstillinger i Godot 4:**
  * `Texture Filter`: **Nearest** (Linear Mipmaps slået fra for at bevare skarpe pixels).
  * `Compress Mode`: **Lossless**.

### 1.2 Farvepalette (Chatty Signature Palette)
For at sikre konsistens på tværs af miljøer og lyssætning er paletten låst til følgende 16-farvers indekserede værdier:

| Token | Hex-kode | Anvendelse |
| :--- | :--- | :--- |
| **Outline** | `#1A1016` | Hård ydre kontur (Dark Plum) |
| **Fur Shadow** | `#C85A17` | Sekundær skygge på krop/ører |
| **Fur Base** | `#F38C2A` | Hovedfarve på Chatty (Tiger Orange) |
| **Fur Highlight** | `#FFB84D` | Toplys, mave og kinder |
| **Whites/Eyes** | `#FFF4E0` | Øjeæbler, tænder, kløer |
| **Pupils/Mouth** | `#3B1E28` | Indre øje, dyb mundhule |
| **Claw FX Base** | `#5CE1E6` | Neon-cyan krads-effekt / Smear frame |
| **Water Blue** | `#38B6FF` | Toilet-vand (Flush animation) |
| **Water Foam** | `#FFFFFF` | Hvirvelskum og dråber |

---

## 2. Frame-by-Frame Nedbrydning af Animationer

Hver animation er tegnet med klassiske animationsprincipper (*Squash & Stretch*, *Anticipation*, *Exaggeration* og *Smear Frames*).

```
   Række 0: [LØB - 8 FRAMES]  ─────────────────────────────────► 12 FPS Loop
   Række 1: [KRADS - 6 FRAMES] ───────────────────────────────► 16 FPS One-Shot
   Række 2: [HOP - 8 FRAMES]  ─────────────────────────────────► Multi-Phase State
   Række 3: [FLUSH - 8 FRAMES] ───────────────────────────────► 10 FPS Gag/Interact
```

---

### 2.1 Række 0: Løb (Run Cycle – 8 Frames, Loop)
*Hastighed: 12 FPS (83.3 ms pr. frame). Fuld kontakt-til-kontakt løbscyklus.*

* **Frame 0 (Kontakt V):** Venstre forpote rammer jorden (X: 18, Y: 44). Kroppen er strakt fremad. Halen bøjer lavt bagud.
* **Frame 1 (Nedslag/Squash V):** Vægten absorberes. Kroppen presses ned 2 pixels (`Y=46`). Hovedet dykker let.
* **Frame 2 (Passerende V $\rightarrow$ H):** Højre bagpote svinger fremad. Kroppen løfter sig.
* **Frame 3 (Afsæt/High Point V):** Fuld luftbåren fase. Halen pisker opad. Begge poter fri af jorden.
* **Frame 4 (Kontakt H):** Højre forpote rammer jorden (spejlet positur af Frame 0).
* **Frame 5 (Nedslag/Squash H):** Vægten absorberes på højre side. 2 px vertikal kompression.
* **Frame 6 (Passerende H $\rightarrow$ V):** Venstre bagpote trækkes frem.
* **Frame 7 (Afsæt/High Point H):** Sekundær luftbåren fase; overgang tilbage til Frame 0.

---

### 2.2 Række 1: Krads (Scratch Attack – 6 Frames, One-Shot)
*Hastighed: 16 FPS (62.5 ms pr. frame). Hurtig, "snappy" nærkampsangreb.*

* **Frame 8 (Anticipation):** Chatty trækker overkroppen tilbage mod højre, samler kløerne, øjnene snævres ind til rovdyrfokus.
* **Frame 9 (Smear/Release):** Ekstrem horizontal *Smear Frame*. Forpoten forvandles til 3 cyan/hvide fartstriber (`#5CE1E6`), der skærer gennem luften i en 45-graders vinkel nedad.
* **Frame 10 (Impact/Active Hitbox):** Kløerne er fuldt udstrakte ved yderposition (X: 42, Y: 32). Her åbnes `AttackHitbox` i koden. Gnister/støvfragmenter sprøjter fra anslaget.
* **Frame 11 (Hold/Follow-through):** Kroppen følger momentum fremad; kløerne decelererer. Hitbox deaktiveres.
* **Frame 12 (Recovery 1):** Chatty trækker poten til sig; ørerne vipper fremad af inertien.
* **Frame 13 (Recovery 2 / Return):** Vender tilbage til neutral balance; klar til ny handling.

---

### 2.3 Række 2: Hop (Jump, Apex & Fall – 8 Frames, State-Driven)
*Opdelt i logiske faser for Godot-state-maskinen.*

* **Jump Anticipation / Pre-jump (1 Frame):**
  * **Frame 16:** Ekstrem squash. Chattys bagdel presses mod jorden (`Y=47`), ørerne lægges fladt bagud.
* **Ascent / Opdrift (2 Frames):**
  * **Frame 17:** Afsæt (*Extreme Stretch*). Kroppen er aflang (højde øget med 4 px), poter peger lodret mod jorden.
  * **Frame 18:** Høj hastighed opad. Vinden griber pelsen og kinderne, halen danner en 'S'-kurve nedad.
* **Apex / Svævefase (2 Frames):**
  * **Frame 19:** Chatty når toppen af parablen. Nul-tyngdekraft. Halen svæver løst opad, ørerne blafrer let.
  * **Frame 20:** Vægtløshedsfokus. Arme og ben spredes let ud for at stabilisere faldet.
* **Descent / Fald (2 Frames):**
  * **Frame 21:** Fald accelererer. Kroppen strækkes let vertikalt, poter og hale peger opad mod faldretningen.
  * **Frame 22:** Fuld faldehastighed (*Terminal Velocity pose*).
* **Landing / Impact (1 Frame):**
  * **Frame 23:** Hård kontakt med underlaget. Kraftig squash, små støvskyer (2 px høje) slår ud til hver side.

---

### 2.4 Række 3: Flush (Toilet/Skyl-ud Gag – 8 Frames, Special Event)
*Hastighed: 10 FPS (100 ms pr. frame). Interaktionssekvens med komisk timing.*

* **Frame 24 (Grib fat):** Chatty hopper op og griber fat i toiletskyl-håndtaget med begge poter.
* **Frame 25 (Håndtag trækkes ned):** Kropsvægten trækker håndtaget i bund. Klik-indikator via 1-pixel hvid blitzlinje.
* **Frame 26 (Vandmasser starter):** En blå vandhvirvel (`#38B6FF`) begynder i bunden af framen. Chatty kigger overrasket ned, pupillerne trækker sig sammen.
* **Frame 27 (Suget tager fat - Vortex):** Chattys underkrop forvrænges i en spiral (sub-pixel rotation/twist). Kløerne klamrer sig desperat til kummen.
* **Frame 28 (Fuld hvirvel):** Kun hovedet og poterne stikker op over vandoverfladen. Hvide skum-bobler (`#FFFFFF`) bobler op.
* **Frame 29 (Slurp / Flush-down):** Chatty suges helt ned med et "POP"-smear, kun halen stikker op i 1 frame.
* **Frame 30 (Vandbobler / Spiral):** Rent vandhvirvel og 4 små bobler, der stiger op.
* **Frame 31 (Efterdønning):** Kummen er tom, en enkelt skumboble sprænger, dryp-effekt.

---

## 3. Spritesheet Koordinat- & Atlas-Matrix

Oversigt over pixelkoordinater i den samlede fil `chatty_spritesheet.png` ($384 \times 192$ px):

```
       Kol 0     Kol 1     Kol 2     Kol 3     Kol 4     Kol 5     Kol 6     Kol 7
      (0,0)     (48,0)    (96,0)   (144,0)   (192,0)   (240,0)   (288,0)   (336,0)
R0: [ Run 0 ] [ Run 1 ] [ Run 2 ] [ Run 3 ] [ Run 4 ] [ Run 5 ] [ Run 6 ] [ Run 7 ]
R1: [ Scrt 0] [ Scrt 1] [ Scrt 2] [ Scrt 3] [ Scrt 4] [ Scrt 5] [ EMPTY ] [ EMPTY ]
R2: [ JmpAnt] [ JmpUp1] [ JmpUp2] [ Apex 1] [ Apex 2] [ Fall 1] [ Fall 2] [ Land  ]
R3: [ Flsh 0] [ Flsh 1] [ Flsh 2] [ Flsh 3] [ Flsh 4] [ Flsh 5] [ Flsh 6] [ Flsh 7 ]
```

---

## 4. Godot 4 Integration (SpriteFrames Opsætning)

For at Apollo eller Atlas kan loade arket direkte i Godot 4 uden konfigurationsfejl, er parametrene for ressource-definitionen fastlagt herunder:

```gdscript
# Anbefalet opsætning i AnimatedSprite2D via kode eller Inspector:
var sprite_frames = SpriteFrames.new()

# Animation: "run"
sprite_frames.add_animation("run")
sprite_frames.set_animation_speed("run", 12.0)
sprite_frames.set_animation_loop("run", true)
# Tilføj frames fra Row 0 (X: 0..7, Y: 0)

# Animation: "scratch"
sprite_frames.add_animation("scratch")
sprite_frames.set_animation_speed("scratch", 16.0)
sprite_frames.set_animation_loop("scratch", false)
# Tilføj frames fra Row 1 (X: 0..5, Y: 1)

# Animation: "jump_anticipation", "jump_up", "jump_apex", "jump_fall", "jump_land"
# Opdeles i diskrete tilstande i SpriteFrames for at muliggøre variabel hoppesystem

# Animation: "flush"
sprite_frames.add_animation("flush")
sprite_frames.set_animation_speed("flush", 10.0)
sprite_frames.set_animation_loop("flush", false)
```

---

## Resumé til Kenneth

1. **Leverance:** Spritesheet-arkitekturen for Chatty er defineret og frame-opdelt til 4 primære animationer: **Løb** (8 frames, loop), **Krads** (6 frames med cyan smear-FX), **Hop** (8 frames opdelt i start, ascent, apex, fald og landing) samt **Flush** (8 frames kaskade/gag-animation).
2. **Standard:** Layoutet benytter et ensartet $48 \times 48$ px gitter på en samlet $384 \times 192$ px atlas-tekstur med bund-centreret pivot og en låst 16-farvers palette.
3. **Klar til spilmotor:** Dataene passer 1:1 til Godot 4's `SpriteFrames` og `CharacterBody2D`, så Apollo kan koble hitboxe og animationsskift på uden offsets eller flimmer på pixels.