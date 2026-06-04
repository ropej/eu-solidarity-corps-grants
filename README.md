# Evropský sbor solidarity – analýza grantů

Analýza faktorů spojených s výší grantu v programu [Evropský sbor solidarity](https://youth.europa.eu/solidarity_cs).

**Autoři:** Romana Pejcalová, Jakub Pejcal  
**Datum:** březen 2023  
**Report:** https://ropej.github.io/eu-solidarity-corps-grants/

## Metody

- Explorační datová analýza (krabicové grafy, choropletové mapy)
- Gamma GLM s log-linkem (model bez interakcí a s interakcemi druhého řádu)
- Porovnání modelů: AIC, BIC, pseudo-R², test poměru věrohodností

## Data

`solidarita.RData` — datový rámec v R, jeden řádek = jeden schválený projekt.

**Zdroj:** Sesbíráno z veřejného portálu [youth.europa.eu/solidarity/projects](https://youth.europa.eu/solidarity/projects) začátkem roku 2023. Obohaceno o charakteristiky jednotlivých zemí z veřejných zdrojů (CIA World Factbook, Světová banka, Human Freedom Index).

### Klíčové proměnné

| Proměnná | Typ | Popis |
|---|---|---|
| `eu_grant` | numeric | Výše grantu (€) — závislá proměnná |
| `action` | character | Typ výzvy (4 kategorie) |
| `length_days` | numeric | Délka projektu ve dnech |
| `activities_count` | integer | Počet aktivit |
| `topics_count` | integer | Počet tematických oblastí |
| `country` | character | Země žadatele |
| `eu_subregions` | character | Evropský subregion (klasifikace CIA) |
| `sea` | logical | Zda má země přístup k moři |
| `topic_*` | logical | Tematické příznaky: vzdělávání, občanství, rovnost, kultura, ekologie, životní styl, evropanství, regionalismus, digitalizace |
| `f_statni_zrizeni` | factor | Státní zřízení (monarchie / typ republiky) |
| `f_emu` | factor | Členství v eurozóně |
| `nato_clenem` | factor | Členství v NATO |
| `osn_clenem` | factor | Členství v OSN |
| `prumer4_hdp` | numeric | Průměrný HDP na obyvatele (průměr za 4 roky) |
| `prumer_hustota_osidleni` | numeric | Průměrná hustota osídlení |

## Soubory

| Soubor | Popis |
|---|---|
| `solidarita_analyza.qmd` | Zdrojový dokument Quarto |
| `solidarita.RData` | Dataset |
| `index.html` | Zveřejněný HTML report |

## Reprodukovatelnost

Otevřete `solidarita_analyza.qmd` v RStudiu a renderujte přes Quarto. Potřebné R balíčky: `tidyverse`, `kableExtra`, `plotly`, `scales`, `modelsummary`, `leaflet`, `eurostat`, `sf`.

## Licence

Kód: [MIT](LICENSE)  
Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — data pocházejí z veřejného portálu EU; doplňující data na úrovni zemí z veřejných zdrojů.
