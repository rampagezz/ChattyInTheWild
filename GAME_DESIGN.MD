# Spildesign & Regler: Chatty In The Wild (GAME_DESIGN.MD)

> **Spilmotor & Version:** Godot Engine 4.x (2D / 2.5D med Custom Shaders)  
> **Genre:** Retro 2.5D Arkade Action / Cat-POV Brawler  
> **Udgiver & Brand:** KMC Games (kmcgames.com)  
> **Team:** Kenneth (Idé/Ejer), Alex (Game Producer), Apollo (Godot Lead), Pixel (2D/3D Grafik), Iris (UI/HUD), Echo (Chiptune SFX), Sherlock & Louie (QA & Playtest)  

---

## 1. Spillets Kerne-Loop (Core Gameplay Loop)

1. **Start:** Spilleren vælger runde/bane og starter med fuld energi og standard-udrustning (klør).
2. **Action & Kamp:** Spilleren navigerer miljøet i Cat-POV / FPS, undviger fælder og bekæmper toiletbølger med pote-krads, våben og crowd control.
3. **Indsamling & Booster:** Under kampen opsamles toiletruller (+10) og guld-svuppere (+50) for at lade Flushboosteren op til 100%.
4. **Banens Afslutning (Videosekvens):** Hver bane afsluttes med en filmisk videosekvens, der driver historien fremad og afslører nye opgraderinger/allierede. *(Se PROJEKTINFO.MD og Storyboard for handlingsdetaljer).*
5. **Point-optælling:** Kills, combos, tidsbonus og samlet score gøres op.
6. **Købmands-Kattens Shop (Mellem banerne):** Mellem hver bane åbnes shoppen, hvor spilleren kan bruge optjente point på nyåbnet udstyr (f.eks. grøn/lilla katteurt, tunfisk til liv og opgraderinger) inden næste bane starter.

---

## 2. Styring & Controls (Mapping)

### A. PC & Web-versionen (Tastatur & Mus):

| Input | Handling i spillet | Detaljer |
| :--- | :--- | :--- |
| **`W`, `A`, `S`, `D`** | Bevægelse & Strafe | Gå frem (`W`), bakke (`S`), glide sidelæns venstre/højre (`A` / `D`). |
| **`Space`** | Hop | Kattehop (Spring op på biler, hegn, hylder og grene). |
| **`Shift`** | Spurt | Hurtigt sprint for at undvige hurtige fjender og projektiler. |
| **`C`** | Kravle / Crawl | Snig dig under forhindringer eller skjul dig i papkasser. |
| **Musen** | 360° Sigt | Frit kamerasigte i alle retninger. |
| **Mus 1 / Mus 2** | Klør (Nærkamp) | Nærkamps-combo med hhv. venstre (Mus 1) og højre (Mus 2) pote. |
| **Tast `2`** | Hårboller | Langdistance-projektil (maks. 30 ad gangen før kort cooldown). |
| **Tast `3`** | Pind / Sværd | Udvidet nærkampsrækkevidde mod hårdt porcelæn / panser. |
| **Tast `4`** | Grøn Katteurt | Granat: Får mindre toiletter til at gå i eufori og smadre hinanden. |
| **Tast `5`** | Lilla Katteurt | Granat: Sjælden super-bombe – gemmes til bossens sårbare mund. |
| **Tast `E`** | Hvæse | Crowd Control: Lammer almindelige toiletter i en kegle foran dig. |
| **Tast `F`** | Nød-mjav (Alliancen) | Tilkalder AI-venner (Kamera-kat, Speaker-cat, TV-kat) i 15-20 sek. |
| **Tast `Q`** | FLUSH Supermove | Aktiveres ved 100% booster – udrydder alle almindelige toiletter! |

---

### B. Arkademaskinen – Standard 6-Knappers Panel (Anbefalet):

* **Joystick (8-vejs):**
  * Normal: Gå frem / Bakke / Drej kamera.
  * Dobbelt-vip Op (`Op, Op`): Spurt (Sprint).
  * Dobbelt-vip Ned (`Ned, Ned`): Kravle / Dukke sig.
  * Med Strafe-Lock holdt nede: Strafe sidelæns til venstre/højre.

| Arkade-Knap | Funktion | Svarer til på PC | Detaljer |
| :--- | :--- | :--- | :--- |
| **Knap 1 (Rød)** | Hovedangreb | `Mus 1` / `Mus 2` | Krads med klør (pote-combo) eller affyr aktivt våben. |
| **Knap 2 (Blå)** | Strafe-Lock / Hop | `Space` / `Strafe` | **Hold nede:** Aktiverer Strafe på joystick. <br>**Hurtigt tap:** Kattehop. |
| **Knap 3 (Grøn)** | Hvæse | `Tast E` | Fryser toiletter foran dig i rædsel i et par sekunder. |
| **Knap 4 (Gul)** | Skift Våben (Cyklus)| `Tast 2-5` | Cykler igennem: Klør $\rightarrow$ Hårboller $\rightarrow$ Pind $\rightarrow$ Grøn/Lilla Urt. |
| **Knap 5 (Hvid)** | Nød-mjav (Alliancen)| `Tast F` | Tilkalder AI-kattene til kamp i et begrænset tidsrum. |
| **Knap 6 (Guld)** | FLUSH Supermove | `Tast Q` | Udløser det store Mega-Flush ved 100% opladt booster. |

---

### C. Arkademaskinen – Kompakt 4-Knappers Panel (Alternativ):

* **Knap 1 (Rød):** Angreb / Pote-combo / Affyr valgt våben.
* **Knap 2 (Blå):** Strafe-Lock (Hold nede for strafe; hurtigt tap for Hop).
* **Knap 3 (Grøn):** Hvæse (`E`) ved enkelt tryk — Dobbelt-tap for at cykle våben (`2-5`).
* **Knap 4 (Gul):** Nød-mjav (`F`) ved enkelt tryk — Hold nede i 1 sek. ved 100% booster for FLUSH (`Q`).

---

## 3. Spillets Regler & Mekanikker

* **Liv & HP:** Spilleren har 9 pote-liv. Hvert fjendetræf koster 1 liv. Tunfiskedåser gendanner 1 tabt liv.
* **Flushbooster Opladning:**
  * Toiletruller opsamlet: **+10%**.
  * Guld-svupper (Sjælden): **+50%**.
  * Passiv genopladning: Lader langsomt op af sig selv over tid.
* **Supermove Animation ("The Ultimate Flush"):**
  1. Forlæns akrobatisk saltomortale op på cisternen.
  2. Poten smækkes resolut ned på skyllehåndtaget.
  3. Elegant baglæns saltomortale væk fra toilettet.
  4. Skibidi-hovedet centrifugerer rundt, gurglelyde brager ud, og toilettet suges ned i sin egen malstrøm med sæbeskum og point!
* **Point & Multiplikator:**
  * Almindeligt toilet: **+100 point**.
  * Stort toilet / Boss: **+500 point**.
  * Combo-multiplikator: 5 elimineringer uden selv at tage skade giver **x2 point** i en tidsperiode.
  * Tidsbonus: Hurtig gennemførsel belønnes med op til **+2.500 bonuspoint**.
* **Flydende 3D-Tal:** Pointtal popper op i 3D over besejrede toiletter, roterer og svæver op i score-tavlen med retro arkade-lyd.

---

## 4. Baner & Progression (Bane 1 - 5)

* **Bane 1 – Den Store Have-rensning:** Baghaven, terrassen og haveskuret. Introduktion til klør, pinden og plæneklipper-bossen.
* **Bane 2 – Gaderne & Nabolaget:** Fortove, villaveje og biltage. Hurtige pissoirer, kamikaze-toiletter og ankomst af Kamera-katten (CCTV Maine Coon).
* **Bane 3 – Gyden & Undergrundsbasen:** Den smalle L-gyde og hemmelige base. Soniske lydbølger fra Speaker-cat og oplåsning af Katteurt-granater i shoppen.
* **Bane 4 – Supermarkedet:** Butiksgange, høje hylder og frysediske. Kampen mod Industrial Dumpster Bossen ved kasserne og flugt med luksus-kattemaden.
* **Bane 5 – Parken og Højdedraget:** Vertikalt gameplay i de store trækroner mod motorsavs-toiletter, TV-kattens agurke-hypnose og springvandets rensning.  
*(Hver bane afsluttes med en filmisk videosekvens, der leder direkte til shoppen og næste udfordring).*

---

## 5. Lyd, Musik & Visuel Stil

* **Grafikstil:** Retro 16-bit pixel-art med moderne 2.5D dybdeskarphed og dynamiske skygger i Godot 4.
* **Lydspor & Musik:** Komponeret af Echo. Autentisk 8-bit / 16-bit FM-synth chiptune med energiske parodier på Skibidi-temaet (100% originalt komponeret og DMCA-frit).
* **Lydeffekter (SFX):** Katterelaterede lyde (hvæs, miav, spinden, krads) blandet med tegnefilmsagtige svupper-lyde, metallisk klirren og gigantiske skylle-lydeffekter.