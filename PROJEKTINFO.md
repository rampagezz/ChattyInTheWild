# PROJEKTINFO.MD - CHATTY IN THE WILD
**Udgiver:** KMC Games (En underafdeling til Lasting Base Studio)  
**Domæne:** [kmcgames.com](https://kmcgames.com)  
**Spilnavn:** Chatty In The Wild  
**Genre:** Retro 2.5D Arkade Action / Horde Brawler  
**Motor:** Godot Engine 4 (2D/2.5D med Pixel/Custom Shaders)  
**Platforme:**  
1. **Fysiske Arkademaskiner** (KMC Games Arcade Cabinets – dedikeret kiosk/arkadepanel)  
2. **PC Standalone** (Windows `.exe` / Linux installer til offline spil og højeste ydelse)  
3. **Web / Browser** (HTML5 WebAssembly / WebGL direkte på kmcgames.com)  
**Målgruppe:** Alle spilglade, retro-fans, børn, unge og arkade-entusiaster.

---

## 1. HISTORIE & PRÆMIS
En solrig eftermiddag i baghaven og den omkringliggende vildmark bliver den velfortjente lur for huskatten **Chatty** brutalt afbrudt. 
En hær af syngende, rullende, fjedrende og flyvende Skibidi-toiletter invaderer hendes territorium! 

Udrustet med sine skarpe kløer, lynhurtige reflekser, kridhvide boksepoter og en uovertruffen evne til at trække ud i toiletterne ("**FLUSH!**"), må Chatty forsvare baghaven, skoven og byen mod invasionen.

---

## 2. HOVEDPERSONEN: CHATTY (1:1 DIGITAL KOPI)
Chatty er baseret direkte på Kenneths rigtige huskat. For at sikre hendes ikoniske udseende skal følgende kendetegn fremgå knivskarpt i både 2D-sprites, illustrationer og 3D-modeller:

* **Hovedet:** Sort "hjelm / pirat-maske" henover ørerne og panden, kombineret med en kridhvid snude og lange, markante hvide knurhår.
* **Halskrave:** En ren, kridhvid ring/krave, der deler den sorte hovedmaske fra kroppens sorte saddel.
* **Højre flanke:** Et unikt hvidt lyn-/zigzag-mønster skåret ind i den sorte ryg (vigtig signatur-detalje, jf. referencefoto `chatty_hoejre_side.jpg`).
* **Poterne:** Kridhvide "boksepoter" på forbenene og fine hvide sokker på bagbenene.
* **Halen:** Helt kulsort, lang, smidig og udtryksfuld (pisker ved angreb, krøller ved sejr).

---

## 3. PLATFORME & DISTRIBUTIONS-STRATEGI

### Kan spillet både køre online og som installerbar PC-version?
**Ja, absolut – og det er den mest optimale strategi!** Da spillet udvikles i **Godot 4**, deler alle versioner præcis den samme kernekodebase og grafik, men eksporteres til tre målrettede udgaver:

| Platform | Format | Formål & Oplevelse |
| :--- | :--- | :--- |
| **1. Web / Online (Browser)** | HTML5 / WebAssembly / WebGL | **Nul installation.** Spilles direkte i browseren på [kmcgames.com](https://kmcgames.com). Perfekt til at fange spillere øjeblikkeligt, dele links på sociale medier eller prøve en bane med det samme. |
| **2. Downloadbar PC-version** | Windows `.exe` / Linux zip | **Maksimal performance & offline-stabilitet.** Kræver ingen internetforbindelse, fjerner browserens hukommelses- og tastaturgrænser, understøtter 120/144Hz skærme samt direkte USB-arkadestiks uden forsinkelse (low latency). |
| **3. Fysisk Arkadekabinett** | Kiosk Mode (Linux/Windows embedded) | Spillet booter direkte i fuld skærm på kabinettet. 100% kontantløst via digital hybrid-betaling: Spontane spillere kan starte øjeblikkeligt via kontaktløst kort eller MobilePay / Apple Pay over QR-kode, mens faste spillere bruger smartphone-app'en **KMC Arcade Games** for at købe fordelagtige spil-pakker. Styres med ægte hardware-knapper og arkade-joystick. |

> **Anbefalet model:** Både en hurtig browser-udgave på websitet for maksimal udbredelse og en installer/download til spillere, der vil have den ultimative, ukomprimerede oplevelse på PC eller arkademaskine.

---

## 4. STYRING & KONTROL-LAYOUT

Spillet kan spilles som **Retro FPS / Cat-POV (Pote-Perspektiv)** eller klassisk arkade, med præcis styring tilpasset både PC/Web og arkadepanel.

### PC & Web-versionen (Tastatur & Mus):

| Kategori | Tast / Input | Handling i spillet |
| :--- | :--- | :--- |
| **Bevægelse & Fysik** | `W`, `A`, `S`, `D` | Gå frem (`W`), bakke (`S`), strafe venstre (`A`) og strafe højre (`D`). |
| **Hop** | `Space` | Kattehop (Spring op på biltage, reoler, frysediske og grene). |
| **Spurt** | `Shift` | Løb ekstra stærkt for at undvige f.eks. hurtige Pissoirer og Kamikaze-toiletter. |
| **Kravle / Crawl** | `C` | Snyg dig under forhindringer, duk dig bag havemure eller skjul dig i papkasser. |
| **Synsvinkel / Sigt** | **Musen** | Drej kamera og sigt frit rundt i 360 grader (Yaw & Pitch). |
| **Klør (Nærkamp)** | **Mus 1 / Mus 2** | Nærkamps-combo med hhv. venstre (Mus 1) og højre (Mus 2) pote! |
| **Arsenal: Hårboller** | **Tast `2`** | Langdistance-projektil (maks 30 ad gangen før kort genladnings-pause). |
| **Arsenal: Pind / Sværd** | **Tast `3`** | Længere rækkevidde end klør – opgraderes til det legendariske Sværd på senere baner. |
| **Arsenal: Grøn Katteurt**| **Tast `4`** | Grøn Katteurt-granat: Får mindre toiletter til at gå i euforisk selvsving og angribe hinanden. |
| **Arsenal: Lilla Katteurt**| **Tast `5`** | Lilla Katteurt-granat: Sjælden og super-potent – gemmes til bossens sårbare mund! |
| **Egenskab: Hvæse** | **Tast `E`** | Lammer almindelige toiletter i en kegle foran dig. Kører på automatisk energi-opladning. *(Virker ikke på bosser!)* |
| **Alliancen: Nød-mjav** | **Tast `F`** | **Friends:** Tilkalder AI-styrede Kamera-, Højtaler- eller TV-katte til at kæmpe ved din side i et tidsrum. |
| **Super Angreb: FLUSH** | **Tast `Q`** | **Mega-Flush Supermove:** Aktiveres ved 100% booster-måler og renser hele skærmen! |

---

### Arkadekabinettet (1-Joystick + Knapper) & "Strafe Lock":

På arkademaskinen sikres præcis samme dybe FPS-manøvredygtighed via en dedikeret **Strafe-Lock knap** og intuitiv knap-allokering:

#### 1. Joysticket:
* **Normal tilstand (Uden knapper holdt nede):**
  * **Op / Ned:** Gå frem / Bakke.
  * **Venstre / Højre:** Drej kamera / Kigger rundt.
  * **Dobbelt-vip Op (`Op, Op`):** Spurt (`Shift` / Dash fremad).
  * **Dobbelt-vip Ned (`Ned, Ned`):** Kravle / Crawl (`C` / Snige sig under forhindringer).
* **Med Strafe-Lock holdt nede (Knap 2):**
  * **Venstre / Højre:** **Strafe sidelæns** (Glide sidelæns til venstre/højre i ægte "Circle-Strafing" rundt om toiletter!).
  * **Op / Ned:** Gå frem / Bakke mens sigtet holdes låst mod fjenden.

#### 2. Standard 6-Knappers Arkadepanel (Anbefalet):

| Arkade-Knap | Funktion | Svarer til på PC | Detaljer |
| :--- | :--- | :--- | :--- |
| **Knap 1 (Rød)** | **Hovedangreb** | `Mus 1` / `Mus 2` | Krads med klør (venstre/højre pote-combo) eller affyr det valgte våben. |
| **Knap 2 (Blå)** | **Strafe Lock / Hop** | `Space` / `Strafe` | **Hold nede:** Aktiverer Strafe på joysticket. <br>**Hurtigt tap:** Kattehop over forhindringer. |
| **Knap 3 (Grøn)** | **Hvæse (Crowd Control)** | `Tast E` | Fryser almindelige toiletter foran dig i rædsel i et par sekunder. |
| **Knap 4 (Gul)** | **Skift Våben (Cyklus)** | `Tast 2-5` / Scroll | Cykler lynhurtigt igennem arsenalet: Klør $\rightarrow$ Hårboller (`2`) $\rightarrow$ Pind/Sværd (`3`) $\rightarrow$ Grøn Katteurt (`4`) $\rightarrow$ Lilla Katteurt (`5`). |
| **Knap 5 (Hvid/Lilla)** | **Nød-mjav (Alliancen)** | `Tast F` | Tilkalder AI-vennerne (Kamera-kat, Højtaler-kat, TV-kat) i 15-20 sek. |
| **Knap 6 (Guld/Orange)**| **FLUSH Supermove** | `Tast Q` | Udløser det altudslettende Mega-Flush ved 100% opladt booster. |

#### 3. Kompakt 4-Knappers Arkadepanel (Alternativ):
Hvis kabinettet kun har 4 knapper, klares alle funktioner med smarte tap/hold-kombinationer:
* **Knap 1 (Rød):** Angreb / Pote-combo / Affyr aktivt våben.
* **Knap 2 (Blå):** Strafe Lock (Hold nede for strafe; hurtigt tap for Hop).
* **Knap 3 (Grøn):** Hvæse (`E`) ved enkelt tryk — Dobbelt-tap for at skifte våben (Cyklus 1-5).
* **Knap 4 (Gul):** Nød-mjav / Friends (`F`) ved tryk — Hold nede i 1 sekund ved 100% booster for at udløse FLUSH Supermove (`Q`).

---

## 5. VÅBENARSENAL & ANSKAFFELSE

Chatty starter med sine naturlige katteevner og opbygger et arsenal gennem banerne:

### 1. Klør (Mus 1 / Mus 2 / Tast `1` / Knap 1 på arkade)
* **Funktion:** Chattys kridhvide forpoter slår ud i lynhurtige 1-2 kradsecombos med venstre og højre pote.
* **Rækkevidde:** Nærkamp.
* **Anskaffelse:** **Altid tilgængelig** fra spillets start.

### 2. Hårboller (Tast `2` / Våbenskift Knap 4 på arkade)
* **Funktion:** Chatty hoster og affyrer hårbolle-projektiler mod fjerne fjender med stor præcision.
* **Rækkevidde:** Langdistance.
* **Magasin & Cooldown:** Chatty har altid adgang til hårboller, men kan skyde **maks 30 hårboller ad gangen før kort cooldown**.

### 3. Pind & Sværd (Tast `3` / Våbenskift Knap 4 på arkade)
* **Pind:** Findes tidligt på **Bane 1**. Giver længere rækkevidde end kløerne og mere slagkraft mod hårdt porcelæn.
* **Sværd:** En legendarisk opgradering gemt væk i en hemmelig trækasse på de **senere baner**. Giver maksimal nærkampsskade og kan skære igennem pansrede toiletter.

### 4. Grøn Katteurt-granat (Tast `4` / Våbenskift Knap 4 på arkade)
* **Funktion:** Kaster en grøn glaskugle med komprimeret kattemynte.
* **Effekt:** Eksploderer i en sky af grøn tåge, der gør mindre toiletter euforiske og forvirrede, så de **begynder at angribe og smadre hinanden**!
* **Anskaffelse:** Låses op i shoppen og overleveres efter Bane 3.

### 5. Lilla Katteurt-granat (Tast `5` / Våbenskift Knap 4 på arkade)
* **Funktion:** Sjælden, mørkglødende og ekstremt potent katteurt-bombe.
* **Effekt:** Gør gigantisk skade på store bosser (f.eks. kastet ind i den åbne mund på Industrial Dumpster Bossen).
* **Anskaffelse:** Låses op i shoppen efter Bane 3.

### 6. Hvæse (Egenskab - Tast `E` / Knap 3 på arkade)
* **Funktion:** Chatty udstøder et frygtindgydende kattespruttende hvæs!
* **Effekt:** Lammer almindelige toiletter i en kegle foran Chatty i et par sekunder. Kører på automatisk energi-opladning *(virker ikke på bosser)*.

### 7. Nød-mjav / Friends (Alliancen - Tast `F` / Knap 5 på arkade)
* **Funktion:** Chatty tilkalder AI-styrede katte (Kamera-, Højtaler- eller TV-kat), der spawner dynamisk i 15-20 sekunder for at hjælpe i kampen. Har cooldown.

---

## 6. FLUSHBOOSTER (SUPER ATTACK OPLADNING)

Superangrebet (`Q` på PC / Knap 3 på Arkade) kræver en fuldt opladt **Flushbooster-måler (100%)**:

### Sådan lades måleren op:
1. **Toiletpapir-ruller:** Samles op på banen eller fra besejrede fjender $\rightarrow$ **+10 til boosteren**.
2. **Guld-svupper (Sjælden):** Sjældent drop fra besejrede toiletter eller skjulte gemmesteder $\rightarrow$ **+50 til boosteren**.
3. **Passiv genopladning:** Flushboosteren lader også langsomt op af sig selv over tid under kampens hede.

---

## 7. SUPERMOVE ANIMATION: "THE ULTIMATE FLUSH"

Når Flushboosteren når 100% og spilleren trykker **`Q`**, udløses en spektakulær filmisk sekvens:

1. **Akrobatisk forlæns saltomortale:** Chatty tager et gigantisk afsæt, roterer forlæns i luften og lander sikkert og stolt oven på cisternen af det invaderende Skibidi-toilet.
2. **Træk i håndtaget:** Med et bestemt blik smækker hun sin kridhvide boksepote ned over det blanke skyllehåndtag på siden!
3. **Baglæns saltomortale:** Chatty kaster sig bagud i en elegant baglæns saltomortale væk fra toilettet.
4. **Vandvirvel & Undergang:** Mens Chatty er vægtløs i luften på vej tilbage:
   * Skibidi-hovedet begynder at snurre vildt og febrilsk rundt som en centrifuge!
   * En overdøvende, gurglende skyllelyd brager ud af højtalerne.
   * Toilettet suges ned i sin egen hvirvlende malstrøm af vand og forsvinder i en eksplosion af sæbeskum og point!

---

## 8. BANE-STRUKTUR, HISTORIE, INTRO-VIDEOER & NØD-MJAV (BANE 1-10)

### Videosekvenser & Overgange (Filmisk Arkade-Flow & Butiks-Unlock):
* **Første videosekvens (Spillets åbning):** Skyder den allerførste bane (Bane 1) dramatisk i gang i baghaven.
* **Efterfølgende videosekvenser ruller i SLUTNINGEN af hver bane:**  
  Når en bane klares, afspilles en filmisk sekvens, der driver historien videre, afslører den næste trussel forude og **introducerer nye allierede eller våben, som låses op i Købmands-Shoppen**!
* **Skippebar:** Alle videosekvenser kan altid skippes øjeblikkeligt med `Space` på PC eller en knap på arkadepanelet.
* **Flow efter hver bane:**
  1. Banen klares $\rightarrow$ Afslutnings-video ruller.
  2. Freeze-Frame med **"NYT UDSTYR / NY ALLIERET LÅST OP!"**.
  3. **Point-optælling (Level Complete):** Kills, combos, tidsbonus og samlet score tælles op.
  4. **Købmands-Kattens Butik:** Spilleren ledes direkte til butikken og kan købe de nyåbnede genstande, opgradere sit arsenal eller fortsætte direkte til næste bane, som starter lynhurtigt i FPS-view!

---

### Nød-mjav Mekanikken (Tilkald Alliancen):
I stedet for at Chatty har en permanent alliance ved sin side, skal hun aktivere sit **"Nød-mjav"** (Tast **`F`** på PC / Knap 5 på arkade).
* **Mekanik:** Chatty har ikke en hær omkring sig hele tiden. Når situationen spidser til, udstøder hun et gennembrydende nød-mjav, hvorefter AI-styrede katte med apparathoveder (f.eks. Kamera-katte, Højtaler-katte, TV-katte) spawner dynamisk fra miljøet (springer ned fra biltage, hopper over hegn eller træder ud af skyggerne).
* **Tidsbegrænset assistance:** Kattene kæmper bravt ved hendes side i et begrænset tidsrum (f.eks. 15-20 sekunder) med unikke evner, hvorefter de trækker sig tilbage. Evnen har en taktisk afkølingstid (cooldown).

---

### 🏡 Bane 1: Den Store Have-rensning

* **Start-videoklip (ca. 15-20 sek. – kan skippes):**
  Chatty ligger og slapper af i den solbeskinnede baghave. Pludselig høres en mærkelig lyd (den velkendte *"Skibidi"*-melodi). Et toilet kommer snigende ud af en busk og nærmer sig Chatty, der overraskes. Det står lynhurtigt klart, at toilettet er fjendtligt og vil angribe. Chatty forsvarer sig resolut med hvæs og krads og slår toilettet ihjel! Flere toiletter vælter nu frem fra buskene – kameraet suser ind i FPS-view, **spilleren overtager styringen**, og Bane 1 er i gang.
* **Miljø & Gameplay:** Chattys trygge baghave, græsplænen, haveskuret og terrassen.
  * *Tutorial & Pinden:* Kradse (`Mus 1/2`), hvæse (`E`) og skyde hårboller (`2`) mod hegnet. Herefter findes **Pinden (`3`)** i et tæt krat.
  * *Haveslangen (Miljøvåben):* Fastmonteret slange ved skuret, der spuler og kortslutter indtrængende toiletter.
  * *Super Attack:* Indsamling af toiletruller og en skjult Guld-svupper for at teste **Super Attack (`Q`)**.
* **Bane-boss – Lawn Mower Cyborg Toilet:** Et gigantisk toilet på en roterende plæneklipper braser igennem hækken. Chatty skal undvige bladene, hoppe op på bossens ryg og kradse cyber-ledningerne over i nakken.
* **Afslutnings-video på Bane 1 (Overgang til Gaderne):**
  Da bossen eksploderer, kastes Chatty bagover og lander i en papkasse, der glider ud på kørebanen/vejen. Papkassen stopper med et ryk på fortovet. Chatty kigger forvirret rundt. 3 Kamikaze-toiletter og 2 Pissoir-toiletter spotter hende! Chatty udstøder et desperat **MJAAVOOOW!**  
  *Freeze-frame:* 👉 *"TRYK PÅ 'F' FOR AT KALDE PÅ HJÆLP! NY ALLIERET: KAMERA-KATTEN (CCTV-MAINECOON)!"*
* **Point-optælling & Shop:** Point tælles op, spilleren kan besøge Købmands-Katten og fortsætter mod Bane 2!

---

### 🛣️ Bane 2: Gaderne & Nabolaget

* **Lyn-start direkte i FPS:** Spillet starter med Chatty i papkassen. Spilleren trykker `F` (eller Knap 5 på arkade) $\rightarrow$ linsezoomlyd (*Zzzt-chik!*) $\rightarrow$ **CCTV-Mainecoon (Kamera-katten)** dumper ned fra busskuret i et tungt superhelte-smald og tænder sit skarpe kameralys, så fjender tager **2x skade**!
* **Miljø & Fjender:** Fortove, kørebaner, væltede skraldespande, parkerede biler og villaveje. Hurtige pissoirer og Kamikaze-toiletter, der forsøger at sprænge biler i luften. Spilleren hopper op på biltage for at undgå trafikken på vejen.
* **Afslutnings-video på Bane 2 (Flugten til Gyden):**
  Kameraet panorerer hektisk hen ad asfalten. Chatty og Kamera-katten løber alt hvad remme og tøj kan holde ned ad villavejen, forfulgt af en massiv horde af Kamikaze-toiletter og pissoirer. Chatty spotter en smal, L-formet gyde og smutter ind med Kamera-katten – men gyden ender ved en tung, låst jerndør! De er spærret inde, og Kamera-katten stiller sig defensivt foran Chatty.  
  Pludselig ryster gyden af en dyb rytmisk bas: På brandtrappen sidder **Højtaler-katten (Speaker-cat)** og spinder synkront med bassen!  
  *Freeze-frame:* 👉 *"NY ALLIERET LÅST OP: SPEAKER-CAT (Udsender soniske lydbølger, der blæser toiletterne bagover!)"*
* **Point-optælling & Shop:** Point tælles op, besøg hos Købmands-Katten, og videre til Bane 3.

---

### 🛢️ Bane 3: Gyden & Undergrundsbasen

* **Lyn-start direkte i FPS:** Kampen starter direkte i den klaustrofobiske L-gyde!
* **Gameplay:**
  1. *Taktisk nærkamp:* Brug Pinden (`3`) til at holde afstand og time Hvæs (`E`) til at lamme forreste række.
  2. *Speaker-cats AI-funktion:* Højtaler-katten skyder kraftige soniske spindelyde (lydbølger) ned gennem gyden og blæser toiletterne bagover.
  3. *Truslen fra parasitterne:* Små parasit-toiletter forsøger at hoppe op på ryggen af AI-kattene for at hjernevaske dem. Chatty skal kradse eller skyde dem af med hårboller!
* **Afslutnings-video på Bane 3 (Leder op til Shoppen & Bane 4):**
  Efter at have overlevet den intense kamp i gyden, smækker Chatty og hendes allierede den tunge jerndør i. De træder ind i den hemmelige undergrundsbase, som er bygget op i et forladt lagerlokale fuldt af teknisk udstyr. Chatty dumper fuldstændig udpumpet ned på et tæppe, og hendes mave knurrer ekstremt højt!  
  En af de tekniske Kamera-katte peger på en stor overvågningsskærm: Skærmen viser det lokale supermarked, hvor Skibidi-toiletterne raserer hylderne og flænser alle poser med kattemad.  
  Kamera-katten åbner en solid metalkasse og tager to glødende glaskugler op: en **Grøn Katteurt-bombe** (Tast `4`) og en sjælden, mørkglødende **Lilla Katteurt-bombe** (Tast `5`). Kamera-katten kigger anerkendende på Chatty med et blik, der siger *"Du ved, hvad du skal gøre"*, giver hende et bestemt nik og lægger bomberne på bordet.  
  *Freeze-frame:*  
  👉 *"NYT UDSTYR LÅST OP I SHOPPEN!"*  
  🟢 **Grøn Katteurt (Tast 4):** Gør fjender euforiske, så de angriber hinanden (perfekt til mindre toiletter).  
  🟣 **Lilla Katteurt (Tast 5):** Sjælden og ekstremt kraftig variant. Gør enorm skade på store bosser!
* **Point-optælling & Shop:** Spilleren ledes direkte til Købmands-Kattens butik, hvor Grøn og Lilla Katteurt nu kan købes til det aktive arsenal!

---

### 🏪 Bane 4: Supermarkedet

* **Start direkte i FPS:** Chatty træder ind gennem supermarkedets bagdør med granaterne klar på tast `4` og `5`.
* **Gameplay i Butiksgangene:**
  * Butiksgangene er proppet med *Shopping Cart Toilets* og svævende *Flying Paper Towel Toilets*.
  * Spilleren bruger den **Grønne Katteurt (Tast `4`)** til at skabe kaos, så toiletterne bliver konfuse og smadrer ind i hinandens porcelæn.
  * Taktisk kat-agility: Hop op på supermarkedets høje hylder og frysediske for at undgå de tunge indkøbsvogne på gulvet.
  * Pas på de brændende køkkenruller fra loftet (fire damage slukkes ved sprunget vandmelon eller is-fryser).
* **Bosskamp ved Kasseapparaterne: Industrial Dumpster Toilet:**
  Ved udgangen venter den gigantiske, inficerede affaldscontainer. Kampen kræver præcis timing og strategi:
  1. *Håndtering af hjælperne:* Containeren spyr konstant mindre toiletter ud. Spilleren holder dem i skak med grøn katteurt (`4`) eller hårboller (`2`) for ikke at blive overmandet.
  2. *Uigennemtrængeligt panser:* Bossen kan **ikke** tage skade på ydersiden af sit pansrede metal (man skal **ikke** gå efter hjulene).
  3. *Timing af "Munden":* Med jævne mellemrum stopper containeren op, og det store metallåg (dens "mund") løftes højt op for at spye madaffald ud over hele området (kun madaffald, ingen affaldssække).
  4. *Det kritiske sårbare vindue:* Lige *inden* containeren spyer madaffaldet afsted, er dens mund vidt åben og sårbar!
  5. *Skades-skalaen:*
     * **Hårboller (Tast `2`):** Giver en *lille* smule skade, hvis man rammer munden.
     * **Grøn Katteurt (Tast `4`):** Giver *middel* skade og distraherer bossen kortvarigt.
     * **Lilla Katteurt (Tast `5`):** Hvis spilleren har sparet op og kaster den **Lilla Katteurt** direkte ind i munden lige inden spyttet, eksploderer den i en massiv lilla røgsky indeni bossen og trækker en gigantisk luns af dens livs-bar!
  6. *Eksplosion:* Når containeren har taget nok skade indvendig fra, eksploderer den i et hav af madaffald, og vejen ud af supermarkedet er banet!
* **Afslutnings-video på Bane 4 (Byparken, Fældning af Træer & TV-Katten):**
  * *Flugten med Kattemaden:* Efter at have sprængt affaldscontaineren i luften med lilla katteurt, slipper Chatty ud gennem supermarkedets vareindlevering med en stor pose luksus-kattemad! Hun løber ind i den tilstødende bypark for at spise i fred og ro under de store træer.
  * *Truslen mod Parken:* Men freden varer kort. Jorden begynder at ryste, og man hører lyden af motorsave og rotorer. En hel hær af **Copter-Toilets (helikopter-toiletter)** og store **gravemaskine-toiletter** vælter ind i parken og begynder brutalt at fælde træerne! Chatty bliver trængt helt op i toppen af et gammelt egetræ, og flere helikopter-toiletter svæver faretruende tæt på hende med ladte lasere.
  * *TV-kattens ankomst:* Pludselig lander en enorm, fluffy, grå perserkat lydløst på grenen ved siden af hende. Den har en gammel billedrørs-skærm som hoved (**TV-katten**). TV-katten kigger roligt på de flyvende toiletter, og dens skærm begynder at gløde i et intenst, lilla og hypnotiserende lys (og viser det ultimative katte-skræmmebillede: en gigantisk agurk!). Helikopter-toiletterne fryser fuldstændig midt i luften af skræk, og deres propeller stopper med at dreje. TV-katten vender sig mod Chatty og blinker med skærmen!
  * *Freeze-frame:* 👉 *"NY ALLIERET LÅST OP: TV-KATTEN (CRT-Perserkat)! (Hypnotiserer og lammer selv flyvende fjender med sin billedrørsskærm!)"*
* **Point-optælling & Shop:** Point tælles op, og spilleren ledes mod Shoppen før Bane 5!

---

### 🌳 Bane 5: Parken og Højdedraget (The Cat Tree Fortress)

* **Miljø:** En stor bypark med tæt skov, gangstier, en sø og gigantiske, gamle egetræer.
* **Starten på banen:** Chatty starter oppe i træerne efter videoen fra Bane 4, hvor TV-katten lige har hypnotiseret de første helikoptere.
* **Gameplay & Lodret Bevægelse (Verticality):** Denne bane tvinger spilleren op i højden! Jorden er dækket af store horder af motorsavs-toiletter, der fælder træerne. Chatty skal bruge sin katte-adræthed til at hoppe fra gren til gren, balancere på wirer og holde sig oppe i trætoppene.
* **Brug af TV-katten (AI - Tast `F` / Knap 5 på arkade):** Når spilleren kalder på hjælp (Tast `F`), spawner den store, fluffy perserkat (**TV-katten**). Den tænder sin billedrørs-skærm, som udsender et hypnotiserende lys (og viser den frygtede agurk!). Alle toiletter i nærheden – både på jorden og i luften – **fryser fuldstændig fast i 5 sekunder**! Det er det perfekte tidspunkt for Chatty til at lade sine Hårboller op eller kaste Katteurt-granater.
* **Nye fjender – "Copter-Toilets":** Flyvende helikopter-toiletter, der skyder med lasere. De forsøger at sprænge de grene, Chatty står på, så hun falder ned til motorsavene på jorden. Spilleren skal skyde dem ned med hårboller eller time sit *Hvæs (Tast `E`)*, som kan kortslutte deres propeller, hvis de kommer for tæt på.
* **Banens finale – Det Syresprøjtende Springvand:** Midt i parken står et stort springvand, som toiletterne har inficeret. Det sprøjter nu med grøn, ætsende syre over hele området. Chatty skal krydse de sidste trætoppe, bruge TV-kattens hypnose til at fryse vagterne, hoppe ned på kontrolpanelet og slå poten hårdt ned i nødstop-knappen for at rense parken!
* **Filmisk Afslutnings-video på Bane 5 (Midtvejs-climax!):**
  * *Triumfen ved Springvandet:* Springvandet stopper med at sprøjte syre og spuler i stedet rent vand ud, hvilket får de resterende park-toiletter til at kortslutte i en stor kædereaktion. Chatty, Kamera-katten, Højtaler-katten og TV-katten samles ved springvandet. De sidder i en cirkel og spiser endelig den velfortjente luksus-kattemad fra supermarkedet. Det er et sjældent, fredeligt øjeblik af triumf.
  * *Moderskibets ankomst:* Pludselig bliver himlen mørk. En enorm mekanisk skygge lægger sig over hele parken. Kattene kigger op i ren rædsel. Højt oppe i luften svæver et **gigantisk moderskib** formet som et futuristisk techno-toilet! Fra bunden af skibet skyder en enorm, rød traktor-stråle (en digital laser) direkte ned mod parken. Strålen rammer de tre AI-allierede: Kamera-katten, Højtaler-katten og TV-katten!
  * *Kidnapningen:* De tre allierede bliver løftet op i luften, mens de mjaver desperat. Chatty springer frem og forsøger at gribe fat i Kamera-kattens hale med sine klør, men strålen er for stærk – de tre allierede bliver suget helt op i moderskibet, som derefter flyver væk mod storbyens skyskrabere i horisonten.
  * *Midtvejs-cliffhanger:* Chatty lander på poterne, helt alene i parken. Hun kigger op mod himlen, hendes knurhår sitrer af vrede, og hun udstøder et dybt, beslutsomt hvæs. Modstandsbevægelsen er blevet kidnappet! Anden halvdel af spillet (Bane 6-10) bliver en stor redningsaktion ind i fjendens hjerte!
  * *Skærmen fryser i et dramatisk mørke:*  
    👉 *"ALLIEREDE KIDNAPPET! (Du kan midlertidigt ikke bruge Nød-mjav på Bane 6... indtil du befrier dem!)"*  
    👉 *"SHOPPEN ÅBNER: Gør dig klar til den store invasion af storbyen!"*
* **Point-optælling & Shop:** Point tælles op, og spilleren ledes mod Shoppen før storby-invasionen i Bane 6!

---

## 9. FJENDER (TOILET-BØLGERNE)

1. **Standard Porcelæn (Wave 1):**  
   Små, luskede porcelænstoiletter, der triller fremad mens de nynner en falsk melodi. Slås ud med 1-2 hurtige potelussinger.
2. **Speed-Toilet / Fjedertoilet (Wave 2):**  
   Udstyret med kraftige fjedre under soklen. De gør pludselige udfald og hopper mod Chatty. Kræver dukke-angreb eller præcise modstød.
3. **Helikopter-Toilet (Wave 3):**  
   Luftbårne toiletter med roterende bræt/propel, der kaster eksplosive toiletpapirs-ruller ned fra oven. Kræver hoppende pote-smæk eller vægspring for at nås.
4. **Sub-Boss – Svupper-Patruljen (Wave 4 & 8):**  
   Mellemstore toiletter der skyder sugekopper ud, som kan låse Chatty fast i et par sekunder.
5. **Boss Wave – Titan Toilet (Wave 5 & 10):**  
   Et massivt, armeret toilet udstyret med roterende stålbørster, dundrende bas og gule laserstråler.  
   *Mekanik:* Spilleren skal først kradse panseret itu, undvige lasere via kassesjul, hoppe op på cisternen og udløse det ultimative **Mega-Flush**!

---

## 10. POINT-SYSTEM & FLYDENDE 3D-TAL

Pointsystemet belønner både præcision, rå overlevelse og hurtighed:

| Handling / Præstation | Point-tildeling | Visuel & Lyd Feedback |
| :--- | :--- | :--- |
| **Almindeligt Skibidi-toilet** | **+100 point** | Gult 3D-pointtal (`+100`) popper op over det knuste toilet og svæver roterende opad. |
| **Hurtigt / Stort toilet (Boss)** | **+500 point** | Stort glødende orange/guld tal (`+500`) eksploderer opad med ekstra stjerne-effekter. |
| **Combo-Bonus (5 kills i træk)** | **2x Multiplier (Dobbelt point)** | Hvis Chatty eliminerer 5 toiletter i træk uden selv at blive ramt, fordobles pointene midlertidigt (f.eks. `+200` / `+1000`). En dynamisk *"COMBO X2!"* flammeblussende tekst vises i HUD'en! |
| **Tids-Bonus (Speedrun)** | **Op til +2.500 bonuspoint** | Ved banens afslutning beregnes en tidsbonus baseret på, hvor hurtigt banen blev gennemført. Hurtigere gennemførsel = markant højere placering på highscoren! |

* **Flydende 3D Point-tal:** Når et toilet elimineres, popper tallet op i 3D lige der hvor toilettet stod, svæver op mod himlen og flyver elegant op i skærmens øverste venstre hjørne, hvor det tæller hurtigt op på den samlede score-tavle med en retro arkade *"pling-pling-pling"* lyd.

---

## 11. LYDDESIGN & SPATIAL AUDIO (RETRO ARKADE-PARODI)

### Den ikoniske Skibidi-sang (Rettigheds- og Parodi-strategi):
* **Juridisk sikkerhed:** Den oprindelige Skibidi-lyd indeholder samplede bidder fra kommerciel popmusik (Timbaland / Biser King). For at KMC Games frit kan udgive spillet på PC, web og fysiske arkademaskiner uden copyright-bøvl eller DMCA-krav, skabes en **100% original Chiptune Arkade-Parodi**.
* **Eksekvering af Echo (Lyddesigneren):** En fængende, pulserende 8-bit/16-bit synth-remix med præcis samme komiske *"brr-skibidi-dop-dop-dop-yes-yes"* rytme, bas-groove og gurgle-stemmer.
* **Spatial 3D Audio (Positionsbestemt lyd):**  
  Jo tættere Skibidi-toiletterne ruller på Chatty, desto højere og tydeligere bliver sangen i kabinen/hovedtelefonerne. Kommer de fra venstre side af haven, høres de tydeligt i venstre højtaler – hvilket fungerer som en genial radar for spilleren!

### Chattys Katte- og Kamplyde:
* **Hårbolle-affyring:** En komisk, tegnefilmsagtig *"Hrrk-PTUI!"* spyttelyd efterfulgt af et piftende projektil.
* **Klør & Pind:** Hurtige kradsende *"Swish-Crack!"* svirp i luften og dundrende træ-knald mod porcelæn.
* **Sværd:** Metallisk *"CLANG!"* og knivskarpe skærelyde med gnist-effekter.
* **Hvæs (Crowd Control):** Et dybt, spruttende, forstærket kattehvæs der ryster skærmen og får fjenderne til at skrige og fryse.
* **Katteurt-granat:** En boblende *"Pfft-KABOOM!"* der udløser en komisk tåge med nynnende, forvirrede toilet-stemmer.
* **Tunfisk & Ekstra Liv:** En hyggelig, dyb spinden fra Chatty og en opløftende arkade-jingle.
* **Supermove (The Ultimate Flush):** En massiv, biograf-rystende *"SSSHHH-GLUG-GLUG-KABLAAM!"* skyllelyd med hvirvlende vandmasser og knusende porcelæn!

---

## 12. HUD, RESSOURCE-BARS & DE 9 LIV

Brugerfladen (HUD) holder spilleren konstant orienteret om Chattys overlevelse og kræfter via 4 dedikerede målere og hendes 9 liv:

### 1. De 9 Hjerteliv (Kattens 9 Liv):
* Chatty starter spillet med **9 hjerter / poteprint** i toppen af skærmen.
* Når hendes **Health-bar** tømmes helt (når "0"), mister hun ét hjerte, hvorefter Health-baren øjeblikkeligt fyldes op igen til 100%.
* Først når alle 9 hjerter er mistet, er det **Game Over** (hvorefter der kan startes et nyt spil via KMC Arcade Games app'en eller restartes på PC/Web).

### 2. Skjold-baren (Panser & Beskyttelse):
* **Hvordan opnås det:** Købes i købmands-butikken for 4.000 point eller findes i hemmelige kasser på banerne.
* **Mekanik:** Skjold-baren fungerer som en forreste stødpude. Når Chatty bliver ramt af flyvende toiletpapir, stik eller bid, **absorberer skjoldet al skade først**!
* Først når skjold-baren er 100% knust og nedbrudt, begynder fjenderne at dræne hendes Health-bar.

### 3. Health-baren (Kattens Modstandskraft):
* Viser Chattys umiddelbare helbred (når hun ikke har et aktivt skjold).
* Drænes af fjendtlige træffere. Kan genopfyldes med fundne tunfiskedåser eller ved at købe en fisk hos Købmands-Katten for 1.500 point.

### 4. Energi / Stamina-bar (Sprint & Turbo):
* **Sprint-funktion:** Ved at holde **`SHIFT`** nede på tastaturet (eller holde Knap 2 på arkadepanelet) kan Chatty spurte og løbe lynhurtigt. Dette er uvurderligt til at lave hurtige modangreb eller flygte fra eksploderende helikopter-toiletter.
* **Begrænsning:** Stamina-baren drænes gradvist under sprint.
* **Genopladning:** Genoplader automatisk langsomt, når Chatty går i almindeligt tempo eller står stille. Kan øjeblikkeligt fyldes helt op ved at spise en **kattegodbid** (500 point).

### 5. Flushbooster-bar (Super Attack Opladning):
* Lades op via toiletruller (+10), guld-svupper (+50) eller købt katteurt (1.500 point). Giver adgang til det altudslettende Mega-Flush med tasten `Q`.

---

## 13. KØBMANDS-KATTEN & BUTIKKEN (SHOP MELLEM BANER)

Når en bane er klaret og haven/skoven er renset for toiletter, panorerer kameraet over i en hyggelig, stemningsfuld retro-butik:

### Atmosfære & Betjening:
* Bag trædisken står en stor, godmodig og **tyk købmands-kat** med forklæde, der byder Chatty velkommen med et venligt spind.
* **Nem Arkade- & PC-navigation:**
  * **Arkade:** Vip joysticket **Op / Ned** for at bladre mellem varerne på hylderne. Tryk på **Knap 1 (Rød)** for at købe!
  * **PC / Web:** Klik direkte med **musen** eller brug piletasterne + `Mellemrum` / `Enter`.

### Varekatalog & Priser:

| Vare i Butikken | Pris | Funktion & Fordel i kampen |
| :--- | :--- | :--- |
| **Kattegodbid** | **500 point** | Fylder øjeblikkeligt **Energi / Stamina-baren** helt op, så Chatty kan sprinte igen. |
| **Grøn Katteurt-granat** | **750 point** *(3 stk: 1.500)* | *(Låst op efter Bane 3)*: Gør fjender euforiske, så de angriber og smadrer hinanden (Tast `5`). |
| **Lilla Katteurt-granat** | **2.500 point** | *(Låst op efter Bane 3)*: Sjælden, super-potent boss-killer. Gør gigantisk skade på bosser (f.eks. i munden på Dumpster Bossen). |
| **Katteurt Blade (Catnip)** | **1.500 point** | Giver et kæmpe boost til **Flushboosteren**, så man hurtigere er klar til sit Supermove (`Q`). |
| **Fisk (Tunfisk)** | **1.500 point** | Lækker fersk tun, der øjeblikkeligt fylder **Health-baren** helt op til 100%. |
| **Slibning af Sværd** | **2.000 point** | *(Kræver at Chatty har fundet sværdet)*: Gør klingen knivskarp, så sværdet forårsager **2x Dobbelt Skade** på alle toiletter resten af spillet! |
| **Katte-Skjold / Rustning** | **4.000 point** | Solid beskyttelsesrustning der tilføjer en fuld **Skjold-bar**, som absorberer alle slag før helbredet tager skade. |

---

## 14. POWER-UPS & BANE-INTERAKTIONER

* **Katteurt (Catnip):** Falder ud af knuste toiletter som grønne, glødende blade. Samles op for at fylde Catnip-måleren og aktivere Knap C (*Flush*).
* **Tunfiskedåser:** Giver Chatty ekstra energi og gendanner 1 tabt pote-liv (Chatty starter med 9 liv, vist som 9 poteprint på skærmen).
* **Papkasser:** Chatty kan dykke ned i spredte papkasser. Når et toilet ruller forbi, kan hun poppe op med et overraskelsesangreb for tredobbelt skade!
* **Væltede Mælkekartoner:** Lækker hvid mælk ud over asfalten/græsset. Fjender der ruller igennem glider ukontrolleret og støder ind i hinanden med komisk effekt.
* **Haveslanger & Vandpøler:** Kan aktiveres for at gøre toiletterne tunge og langsomme.

---

## 15. HIGHSCORE-TAVLE (RETRO ARKADE)

* **Klassisk Highscore-system:** Spillet har sin egen indbyggede highscore-tavle, som kører uafhængigt direkte på maskinen/PC/Web.
* **Klassisk 3-bogstavs initialer:** Spillere indtaster deres navn i ægte retro-stil (f.eks. `KMC`, `CAT`, `DAN`) med joysticket eller piletasterne.
* **Top 10 Rekordliste:** Gemmer de bedste scores lokalt på kabinettet/enheden, hvilket driver motivationen til at spille igen og slå rekorden.

---

## 16. TEAMETS ROLLER & LEVERANCER (AGENT_FLOW)

* **Alex (Teamleder):** Overordnet roadmap, koordinering, deadlines og funktionsprioritering.
* **Apollo (Godot 4 Udvikler):** Spilmotorkerne, arkadestyring, fysik, bølge-spawner, eksportopsætning (WebAssembly + PC Desktop + Kiosk).
* **Pixel (2D Sprite Artist):**  
  * `chatty_spritesheet.png` (Idle, Løb, 3-hit pote-combo, Ninja-hop, Flush-supermove).  
  * `toilet_enemies.png` (Standard, Fjeder, Helikopter, Svupper, Titan Boss).  
* **Iris (Grafisk Designer & UI):** Arkade HUD, 9 pote-livsikon, Catnip-meter, retro-font, KMC Games overlay og Highscore-skærm.
* **Geppetto (3D-snedker & Miljø):** Baggrunde i 2.5D, dybdelag, rekvisitter samt 3D-kabinetsvisualisering til markedsføring.
* **Echo (Lyddesigner):** Arkade-chiptune temaer, autentiske spinde- og hvæselyde, tegnefilms-svupper og voldsomme toiletskyls-lydeffekter.
* **Sherlock & Louie (QA, Balance & Playtest):**  
  * *Sherlock:* Kodediagnostik, input-latency, WebAssembly-kompatibilitet og kollisionsfejl.  
  * *Louie:* Sværhedsgrad, underholdningsværdi, morskabsfaktor og arkade-følelse!

