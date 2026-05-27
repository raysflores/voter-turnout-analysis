# Virginia Voter Turnout — County-Level Regression Analysis

**Ray Santiago Flores, Natalie [last name], Ashley [last name] · Applied Regression Analysis · Summer 2025 · University of Virginia**

A multiple linear regression analysis of 2024 general election voter turnout across Virginia's counties and independent cities, drawing on socioeconomic, demographic, and labor market data from six federal and state data sources.

---

## Overview

Virginia recorded approximately 4.5 million votes cast in the 2024 general election out of 6.4 million registered voters — a 70.5% turnout rate. But that aggregate masks substantial variation across the state's 133 counties and independent cities. This project builds a regression model to identify which measurable county-level characteristics predict voter participation rates, using data compiled from NIH, USDA, BEA, BLS, ODGA, the Virginia Department of Elections, and the U.S. Census Bureau.

---

## Research Questions

1. Does voter proportion vary significantly by county educational attainment?
2. Do median household income, population density, and labor market conditions predict turnout?
3. Does county dominant industry type (manufacturing, government, farming, etc.) explain residual variation after controlling for demographics?

---

## Data Sources

| Variable | Source |
|---|---|
| Voter turnout by county (2024) | Virginia Department of Elections |
| Median household income, population density | National Institute on Minority Health (2019–2023 avg.) |
| Labor force, employment, unemployment | Virginia ODGA |
| Education (% bachelor's or higher) | U.S. Department of Education (2023) |
| Average weekly wage | Bureau of Labor Statistics |
| County dominant industry typology | USDA Economic Research Service (2025) |
| County GDP | Bureau of Economic Analysis |

---

## Methods & Technical Stack

- **Language:** R
- **Key packages:** `readr`, `corrplot`, `tidyverse`, `ggplot2`
- **Statistical methods:**
  - Multiple linear regression (OLS)
  - Correlation analysis (`corrplot`)
  - Categorical variable encoding (education attainment, wage range, urban/rural, industry type, population size)
  - Residual diagnostics

---

## Key Variables

**Continuous predictors:** median household income, population density, labor force size, unemployment rate, county GDP

**Categorical predictors:**
- `education` — binary (≥50% of county holds bachelor's degree or higher)
- `avg_weekly_wage` — four-level ordinal (≤$949 / $950–$1099 / $1100–$1249 / ≥$1250)
- `urban_rural` — U.S. Census Bureau classification
- `pop_range` — small / medium / large (quartile-based)
- `dominant_industry` — USDA typology: farming, manufacturing, government, mining, recreation, unspecified

**Outcome:** `VoterProportion` — total votes cast / registered voters, by county

---

## Repository Structure

```
├── Knitted.Rmd                       # Final analysis report (R Markdown)
├── PROP.Final Exec Document.Rmd      # Executive summary version
├── data/
│   ├── Final_Data_Modified2.csv      # Master merged dataset (all counties)
│   ├── Final_Data.csv                # Primary data
│   ├── Median Household income.csv   # NIH/Census income data
│   ├── bls_unemployment_by_month_county.csv  # BLS labor data
│   └── CountyGDP.xlsx                # BEA county GDP
└── output/
    └── Regression Project Sub.pdf    # Final submitted report
```

---

## About

Completed as the final project for Applied Regression Analysis at the University of Virginia. Analysis is specific to the 2024 Virginia general election.

**Authors:** Ray Santiago Flores, Natalie, Ashley
