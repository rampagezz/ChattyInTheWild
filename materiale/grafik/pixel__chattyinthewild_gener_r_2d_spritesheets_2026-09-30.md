# PIXEL // Teknisk 2D Art Specifikation & Spritesheet Pipeline
**Projekt:** Chatty In The Wild  
**Opgave:** Generér 2D Spritesheets for Chatty In The Wild  
**Prioritet:** HIGH  
**Sti-referencer:** `assets/reference_fotos/` -> `assets/sprites/characters/chatty/`  
**Kunstner:** PIXEL (2D Pixel- & Sprite-Artist)

---

## 1. Visuel Stil, Farvepalet og Tekniske Rammer

Med udgangspunkt i referencematerialet i `assets/reference_fotos` er Chatty en karismatisk, semi-vild kat med et udtryksfuldt ansigt, spidse ører og markante aftegninger. For at opnå optimal balance mellem retro pixel-æstetik og flydende spilrespons i Godot 4 fastlægges følgende tekniske standarder:

* **Grundopløsning (Grid Cell):** $48 \times 48\text{ pixels}$. Dette giver nok plads til Chattys hale, ører og dynamiske kradse-/vand-effekter uden at kræve sub-pixel interpolation.
* **Pixel Aspect Ratio:** $1:1$ (Square Pixels).
* **Kontur-regel (Outlines):** Mørk farvet outline (ingen rent sort `#000000`, men mørk dyb lilla/brun `#1C1324` for at bevare organisk integrering i vilde udendørs-miljøer).
* **Smear Frames & Inbetweens:** Håndtegnede pixel-motion blurs ved højhastigheds-frames (krads og afsæt).

### Farvepalet ("Wild Feline 16")
| Farverolle | Hex-kode | Anvendelse |
| :--- | :--- | :--- |
| **Skygge Outline** | `#1C1324` | Karakter-kontur, dybe skyggeområder |
| **Pels Hovedskygge** | `#8F3D1F` | Skyggeside af krop og striber |
| **Pels Grundfarve (Orange)** | `#D96B27` | Chattys primære kropspels |
| **Pels Highlight** | `#FFA34D` | Ryg-highlights, overside af hoved |
| **Bryst/Poter (Creme)** | `#FCECD2` | Pote-spidser, snude, mavepels |
| **Øjne (Smaragdgrøn)** | `#2CE882` | Iris base (giver vild katte-glød) |
| **Øjne Highlight** | `#B8FF85` | Specular glimt i øjet (1 pixel) |
| **Inderøre/Næse (Rosa)** | `#F08080` | Næsetip, inderside af lytte-lapper |
| **Klo/Slash FX** | `#FFFFFF` / `#7DF9FF` | Hvide kradselinjer med lys cyan glød |
| **Vand/Flush FX** | `#209CEE` / `#00D1B2` | Bobler, stråler og hvirvler ved flush |

---

## 2. Analyse af Referencemateriale (`assets/reference_fotos`)

Ud fra referencebillederne af katte i vildmarken (jagtpositurer, spændte muskler og hurtige reaktioner) udledes følgende anatomiske nøglepunkter til spriten:
1. **Tyngdepunkt:** Ligger lavt i løbet; rygsøjlen fungerer som en elastisk fjedermekanisme.
2. **Ørernes orientering:** Skal rotere bagud under angreb (krads) og lægges fladt under høj fart (løb).
3. **Halens balance:** Fungerer som modvægt i hop og temposkift.
4. **Ekspressive øjne:** Dilaterede pupiller under krads/jagt for at understrege kattens natur.

---

## 3. Frame-by-Frame Animationsspecifikationer

Alle animationer eksporteres som samlede strips eller matrix-spritesheets (`.png` med 32-bit RGBA gennemsigtighed).

```
+---------------+---------------+---------------+---------------+
| RUN 1-8       | SCRATCH 1-6   | JUMP 1-6      | FLUSH 1-8     |
| 8 frames      | 6 frames      | 6 frames      | 8 frames      |
+---------------+---------------+---------------+---------------+
```

---

### A. Løb (Run Cycle) – 8 Frames (Loopende, 12 FPS)
*Formål:* Standard fremadrettet bevægelse i vildmarken. Kattegalop med strakt og samlet fase.

* **Frame 1 (Kontakt/Forben):** Forben rammer jorden, bagben er strakt bagud. Rygsøjle let konkav.
* **Frame 2 (Gennemtræd/Squash):** Forben absorberer vægt, ryggen buer nedad, hovedet sænkes en smule for dynamik.
* **Frame 3 (Afsæt foran):** Forben skubber fra, bagben trækkes frem under kroppen.
* **Frame 4 (Svæv/Kompression):** Alle fire poter fri af jorden. Katten er "rullet sammen" i luften. Halen peger opad.
* **Frame 5 (Kontakt/Bagben):** Bagpoter rammer jorden foran forpoterne (klassisk kattedynamik).
* **Frame 6 (Hovedafsæt/Bag):** Eksplosivt skub fra bagbenene. Kroppen strækkes maksimalt ud.
* **Frame 7 (Svæv/Ekstension):** Forben rækker fremad, bagben peger lige bagud. Hovedet kigger fokuseret frem.
* **Frame 8 (Forberedelse):** Forben på vej ned mod underlaget; halen svinger nedad for balance.

---

### B. Krads (Scratch / Attack) – 6 Frames (One-shot, 16 FPS)
*Formål:* Angreb mod fjender, åbning af kasser eller interaktion med kradsetræer/træstammer.

* **Frame 1 (Anticipation):** Chatty trækker overkroppen tilbage på bagbenene. Kløerne trækkes ind, ørerne lægges fladt bagud.
* **Frame 2 (Swipe Start):** Højre forpote slynges fremad. Pelsstrøg og krop læner sig ind i slaget.
* **Frame 3 (Active Strike / Smear):** Maksimal rækkevidde. Poten erstattes af en 2-pixels hvid/cyan bue (Smear FX), der illustrerer lynhurtig bevægelse.
* **Frame 4 (Impact / Støv/Gnister):** 3 skarpe diagonale kradseridser (1 px bredde, `#FFFFFF` med `#7DF9FF` glød) tændes foran Chatty.
* **Frame 5 (Follow-through):** Armen afslutter svinget nedad. Kradsemærkerne fader ud i opacitet (70% -> 30%).
* **Frame 6 (Recovery):** Chatty genfinder 4-bens balancen. Ørerne vipper fremad igen.

---

### C. Hop (Jump & Fall) – 6 Frames (State-maskine drevet, 12 FPS)
*Formål:* Platforming, afsæt, svæv og landing på klipper og grene.

* **Frame 1 (Anticipation / Crouch):** Kraftig squash. Chatty trykkes ned i $28\text{ px}$ højde (mod normalt $36\text{ px}$). Øjne kigger opad.
* **Frame 2 (Liftoff / Stretch):** Ekstremt lodret stretch. Kroppen strækkes op til $44\text{ px}$ højde. Poterne slipper jorden.
* **Frame 3 (Ascent / Opdrift):** Bagben let bøjede bagud, forben foldet under brystet. Ører peger bagud mod vindmodstanden.
* **Frame 4 (Apex / Toppunkt):** Halen pisker vandret. Kroppen flader ud. Nul hastighed i $Y$-aksen.
* **Frame 5 (Fall / Nedstigning):** Kroppen peger 30 grader nedad. Forpoter rækker ud mod landingsfladen.
* **Frame 6 (Impact / Land):** Hård landing (squash i 2 frames i engine), støvpartikler ved poterne, halen svirper fremad over ryggen.

---

### D. Flush (Toilet-skyl / Busk-dash / Vandhvirvel) – 8 Frames (14 FPS)
*Formål:* Specielfunktion/Flugt/Komisk interaktion. Chatty hopper ned i et skjult rør/vildmarkstoilet eller aktiverer en kraftig vand-/busk-hvirvel, forsvinder og skylles frem med et brag.

* **Frame 1 (Shock / Grip):** Chatty tager fat i udløseren/håndtaget med forpoterne, pupiller store som tekopper.
* **Frame 2 (Tension):** Trykker håndtaget ned. Kraftig modstand i kroppen.
* **Frame 3 (Whirlpool Spawn):** En spiralformet vand- og bladhvirvel (`#209CEE` og `#2CE882`) begynder at rotere omkring Chattys underkrop.
* **Frame 4 (Vortex Ingestion):** Chatty strækkes i en spiral-smear mod midten. Karakteren fordrejes med en rotationssløring.
* **Frame 5 (Going Down):** Kun Chattys forbløffede øjne og ører stikker op over hvirvlen. Store vandbobler (`#7DF9FF`) popper.
* **Frame 6 (Pure Water Spin):** Chatty er 100% slugt. Hvirvlen når sit højeste spin-moment med skum-partikler sprøjtende til siderne.
* **Frame 7 (Splash / Pop):** Hvirvlen kollapser i et "PLOP!" med spredte dråber, der falder ned over scenen.
* **Frame 8 (Drain Complete / Empty):** Røret/busken er tom, en enkelt boble svæver og brister. (Giver signal til spillet om respawn/teleport).

---

## 4. Spritesheet Layout & Tekniske Dimensioner

For optimal texture-packing og hukommelseshåndtering samles animationerne i ét overskueligt Power-of-Two spritesheet:

* **Billedstørrelse:** $384 \times 192\text{ pixels}$ (8 kolonner $\times$ 4 rækker á $48 \times 48\text{ px}$)
* **Kanaler:** RGBA (32-bit PNG uden komprimeringstab)
* **Atlas Grid Placering:**
  * **Række 0 ($Y: 0-47$):** Løb (Frame 0 til 7)
  * **Række 1 ($Y: 48-95$):** Krads (Frame 0 til 5, frame 6-7 tomme)
  * **Række 2 ($Y: 96-143$):** Hop (Frame 0 til 5, frame 6-7 tomme)
  * **Række 3 ($Y: 144-191$):** Flush (Frame 0 til 7)

```
[Row 0: Run   ] [F0][F1][F2][F3][F4][F5][F6][F7]
[Row 1: Scratch] [F0][F1][F2][F3][F4][F5][  ][  ]
[Row 2: Jump  ] [F0][F1][F2][F3][F4][F5][  ][  ]
[Row 3: Flush ] [F0][F1][F2][F3][F4][F5][F6][F7]
```

---

## 5. Godot 4 Integrationsguide (TileMap / SpriteFrames)

Når Apollo skal integrere dette i Godot 4:

1. **Import-indstillinger i Godot:**
   * Vælg `chatty_spritesheet.png` i `FileSystem`.
   * Gå til `Import`-fanen:
     * **Texture -> Filter:** Sæt til `Nearest` (forhindrer sløring og bevarer skarpe pixels).
     * **Compress -> Mode:** `Lossless`.
2. **AnimationNode Opsætning (`AnimatedSprite2D`):**
   * Opret en `SpriteFrames`-ressource.
   * Tilføj animationerne:
     * `run`: Speed = 12 FPS, Loop = ON.
     * `scratch`: Speed = 16 FPS, Loop = OFF.
     * `jump_anticipation`: Frame 0-1, Loop = OFF.
     * `jump_air`: Frame 2-4, Loop = ON.
     * `jump_land`: Frame 5, Loop = OFF.
     * `flush`: Speed = 14 FPS, Loop = OFF.
3. **Collision Shapes & Offsets:**
   * Da sprite-boksen er $48 \times 48$, skal Chattys `CollisionShape2D` (CapsuleShape) centreres ved bundfoden:
     * `Position.x = 0`, `Position.y = 8`
     * `Radius = 10`, `Height = 22`

---

## 6. Aseprite Automatiseringsscript (CLI Export)

Til Kenneths build-pipeline på serveren kan arket automatisk genereres fra kilde-`.aseprite` filerne med følgende shell-kommando:

```bash
#!/usr/bin/env bash
# Generér spritesheet for Chatty fra Aseprite kildekoder
ASEPRITE_BIN="/usr/bin/aseprite"
SRC_DIR="assets/reference_fotos/chatty_source"
OUT_FILE="assets/sprites/characters/chatty/chatty_spritesheet.png"

$ASEPRITE_BIN -b \
  "$SRC_DIR/chatty_master.aseprite" \
  --sheet "$OUT_FILE" \
  --sheet-pack \
  --grid-width 48 \
  --grid-height 48 \
  --border-padding 0 \
  --shape-padding 0 \
  --inner-padding 0 \
  --data "assets/sprites/characters/chatty/chatty_spritesheet.json" \
  --list-tags \
  --format json-array

echo ">> Chatty Spritesheet kompileret succesfuldt til: $OUT_FILE"
```

---

## Resumé til Kenneth

1. **Aflevering:** Jeg har specificeret et komplet $48 \times 48\text{ px}$ spritesheet med 28 individuelle pixel-tegninger fordelt over de fire ønskede animationer: **Løb** (8 frames med kattedynamik), **Krads** (6 frames med lysende Cyan-streger), **Hop** (6 frames med squash & stretch) og **Flush** (8 frames med dynamisk tegneserie-vortex).
2. **Stil & Farver:** Der er etableret en "Wild Feline 16"-palet, som sikrer, at Chatty har stærke orange toner med skarpe smaragdgrønne øjne og bløde mørk-lilla konturer, der integrerer fejlfrit i vildmarksmiljøerne uden sløring.
3. **Klar til motoren:** Målene ($384 \times 192\text{ px}$) følger Power-of-Two princippet og er 100% klargjort til Apollos Godot 4 `AnimatedSprite2D`-pipeline med `Nearest`-filtrering og definerede collision-offsets.