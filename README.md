# Canada-STIR

Interactive Tableau dashboard analyzing housing affordability in Canada using the STIR metric.

---

## Project overview

This repository contains the analyses, cleaned data, and visual assets used to build an interactive Tableau dashboard that explores housing affordability across Canada (by province, age group, and education). Key insight from the analysis: young adults face the highest housing burden.

Tableau dashboard (public): [https://public.tableau.com/app/profile/jiale.shen/viz/shared/D95T69T8P]

---

## Contents

- data/  
  - raw/ — original census extracts (2016 & 2021) **(not included)**  
  - cleaned/ — cleaned datasets used for analysis
- scripts/  
  - 01_clean_data.R — data cleaning and harmonization (R)  
  - 02_compute_stir.R — STIR metric construction and aggregation (R)  
  - 03_analysis_plots.R — exploratory plots and summary tables (R)
- tableau/  
  - dashboard.twbx — packaged Tableau workbook (or link to public viz)
- README.md

(Adjust folder names above to match the repository structure if different.)

---

## Data

Sources:
- Canadian Census 2016 & 2021 (Public use / tabulated extracts)
- All data used here were cleaned and harmonized in R to ensure consistent geography and variable definitions across census years.

Important: Raw census files are large and are not included in this repo. See `scripts/01_clean_data.R` for the steps to download and preprocess the raw census extracts.

---

## Methodology

- STIR metric (Summary of housing TRends or similar — replace with your formal definition) was constructed to quantify housing burden across population groups.
- Aggregations performed by:
  - Province / territory
  - Age group (e.g., 15–24, 25–34, ...)
  - Education level
- Harmonization steps include:
  - Matching geographic boundaries across 2016 and 2021
  - Standardizing income and housing-cost variables
  - Weighting using census sample weights where appropriate

(If you have a formal STIR definition, include that formula/description here.)

---

## Reproducing the analysis

Prerequisites:
- R (>= 4.0)
- R packages: tidyverse, sf (if using spatial), janitor, readr, dplyr, tidyr, survey (if weighting), and other packages used in scripts.

Basic steps:
1. Clone the repo:
   - git clone https://github.com/tingting020/Canada-STIR.git
2. Place raw census files (if you have them) into `data/raw/`.
3. In R:
   - set your working directory to the repo root
   - run `scripts/01_clean_data.R` to generate cleaned datasets in `data/cleaned/`
   - run `scripts/02_compute_stir.R` to compute STIR and create aggregated tables
   - run `scripts/03_analysis_plots.R` to produce summary plots and export CSVs used by Tableau
4. Open `dashboard.twbx` in Tableau or publish to Tableau Public. Alternatively, use the public link above.

Notes:
- If you do not have the raw census extracts, you can still open the cleaned datasets in `data/cleaned/` (if provided) to reproduce visualizations.

---

## Visualization

- The interactive dashboard is built in Tableau. It consumes the aggregated CSVs produced by the R analysis scripts.
- Public view: https://public.tableau.com/xxxxxx
- Recommended Tableau fields and filters: Province, Age group, Education, STIR, household income quintile, housing cost ratio.

---

## Key findings (summary)

- Young adults face the highest housing burden.
- (Add more bullet points from your analysis: e.g., geographic patterns, education effects, trends between 2016 and 2021.)

---

## Contributing

Contributions, issues, and feature requests are welcome. For changes to analysis scripts, please:
1. Open an issue describing the proposed change.
2. Create a branch and a PR with clear description and reproducible steps.

---

## License

Suggested: MIT License — include a `LICENSE` file if you want this. (Ask if you'd like me to add one.)

---

## Contact

Repository owner: tingting020  
For questions or to request the original data, contact: https://github.com/tingting020

---
