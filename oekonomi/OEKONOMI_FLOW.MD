# Økonomi Flow & Retningslinjer: Lasting Base Studio & ChattyInTheWild

> **Ansvarlig ledelse:** Kenneth (CEO & Ejer)  
> **Økonomi-team:** Penny (CFO), Tally (Driftsbogholder), Tribute (Monetisering), Heimdal (Bank-Gatekeeper), Vera (Statsrevisor)  
> **Officiel e-mail:** kmc@lastingbasestudio.dk (Monitoreres af Vera)  
> **Bankforbindelse:** Danske Bank Erhverv (District) via officiel MCP (Model Context Protocol)  
> **Regnskabsprogram:** Dinero API (Årsrapport & Moms)

---------------------------

## 🏛️ Teamets Roller og Ansvarsfordeling

### 1. Penny (CFO & Budget Lead)
- **Opgave:** Overvåger den overordnede likviditet og udarbejder P&L (Profit & Loss) for alle projekter.
- **Rapportering:** Leverer månedlige cashflow-prognoser og advarer proaktivt, hvis faste udgifter overstiger budgettet.
- **Mandat:** Rådgivende. Alle større budgetjusteringer forelægges Kenneth i Godkendelses-Loopet.

### 2. Tally (Driftsbogholder)
- **Opgave:** Registrerer og kategoriserer alle løbende driftsomkostninger (Nordicway webhotel, domænegebyrer, servernoder, AI-token forbrug).
- **Samspil med Support:** Modtager automatisk besked fra Vance ved godkendte refusioner og modregner dem i projektets resultat.
- **Bilagsmatch:** Sikrer, at der er kvittering på samtlige korttræk.

### 3. Tribute (Monetisering & Prisstrateg)
- **Opgave:** Maksimerer indtjeningen på spil og platforme (GreedyMania, GravesEcho, Preplager m.fl.).
- **Overvågning:** Følger Google Play 15% platform-cut, Stripe-gebyrer, konverteringsrater på In-App Purchases (IAP) og eCPM på belønningsreklamer.
- **Prissætning:** Udarbejder anbefalinger til priser på in-game valuta, terning-skins og abonnementer.

### 4. Heimdal (Bank-Gatekeeper & Sikkerhedsvogter)
- **Opgave:** Styrer den tekniske bro til **Danske Bank MCP** med mTLS-certifikater og OAuth.
- **Urokkelig Sikkerhedsregel:** Heimdal har udelukkende **læse- og afstemningsadgang** (hentning af saldi og transaktioner). 
- **Betalingsspærring:** Hverken Heimdal eller andre agenter kan trække penge ud af banken. Enhver betaling skal godkendes af Kenneth personligt i Danske Bank District med MitID.
- **Revisionsspor (Audit Trail):** Logger hvert eneste API-kald med tidsstempel, udløser og formål.

### 5. Vera (Statsrevisor & Myndighedsansvarlig)
- **Opgave:** Styrer Dinero API, bogføring, momsopgørelser og klargøring af den officielle årsrapport til Erhvervsstyrelsen.
- **Officiel Mail (kmc@lastingbasestudio.dk):** Vera overvåger denne mailkonto for fakturaer, breve fra Skattestyrelsen og officielle bekræftelser.
- **Automatisk Fakturahåndtering:** Indgående PDF-fakturaer på `kmc@` analyseres, oprettes som udgiftsbilag i Dinero og matches med bankposteringerne fra Heimdal.

---------------------------

## 🔄 Det Daglige Økonomi-Loop

```
[Faktura modtaget på kmc@] ➡️ [Vera scanner & opretter i Dinero]
                                           ⬇️
[Beløb trækkes i Danske Bank] ➡️ [Heimdal henter linje via MCP] ➡️ [Vera foretager bankafstemning]
                                                                                ⬇️
[Tally bogfører projektudgift] ⬅️ [Penny opdaterer likviditetsoverblik] ⬅️ [Grønt flueben i Dinero]
```

---------------------------

## 📜 Logning og Gennemsigtighed
Alle interne drøftelser, bilagsafstemninger og budgetvurderinger mellem Penny, Tally, Tribute, Heimdal og Vera logges automatisk i:
`/storage/standard/projekter/ChattyInTheWild/oekonomi/dialoger/`
