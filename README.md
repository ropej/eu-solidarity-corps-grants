# EU Solidarity Corps – Grant Analysis

Analysis of factors associated with grant amounts in the [European Solidarity Corps](https://youth.europa.eu/solidarity_cs) programme.

**Authors:** Romana Pejcalová, Jakub Pejcal  
**Date:** March 2023  
**Report:** https://ropej.github.io/eu-solidarity-corps-grants/

## Methods

- Exploratory data analysis (boxplots, choropleth maps)
- Gamma GLM with log link (model without interactions and with second-order interactions)
- Model comparison: AIC, BIC, pseudo-R², likelihood ratio test

## Data

`solidarita.RData` — R data frame with 1 row per approved project.

**Source:** Scraped from the public portal [youth.europa.eu/solidarity/projects](https://youth.europa.eu/solidarity/projects) in early 2023. Enriched with country-level characteristics from public sources (CIA World Factbook, World Bank, Human Freedom Index).

### Key variables

| Variable | Type | Description |
|---|---|---|
| `eu_grant` | numeric | Grant amount (€) — outcome variable |
| `action` | character | Type of action call (4 categories) |
| `length_days` | numeric | Project duration in days |
| `activities_count` | integer | Number of activities |
| `topics_count` | integer | Number of thematic areas |
| `country` | character | Applicant country |
| `eu_subregions` | character | European subregion (CIA classification) |
| `sea` | logical | Whether the country has sea access |
| `topic_*` | logical | Thematic flags: education, citizenship, equality, culture, ecology, lifestyle, europeanism, regional, digital |
| `f_statni_zrizeni` | factor | State system (monarchy / republic type) |
| `f_emu` | factor | Eurozone membership |
| `nato_clenem` | factor | NATO membership |
| `osn_clenem` | factor | UN membership |
| `prumer4_hdp` | numeric | Average GDP per capita (4-year mean) |
| `prumer_hustota_osidleni` | numeric | Average population density |

## Files

| File | Description |
|---|---|
| `solidarita_analyza.qmd` | Quarto source document |
| `solidarita.RData` | Dataset |
| `index.html` | Published HTML report |

## Reproducibility

Open `solidarita_analyza.qmd` in RStudio and render with Quarto. Required R packages: `tidyverse`, `kableExtra`, `plotly`, `scales`, `modelsummary`, `leaflet`, `eurostat`, `sf`.

## License

Code: [MIT](LICENSE)  
Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — data originates from a public EU portal; country-level enrichment from public sources.
