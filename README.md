# DATA 205 Capstone Project: Montgomery County Dispatch & Crime Analysis (2025)
---

## Project Overview

When you call 911 in Montgomery County, how long until an officer arrives — and what
determines that wait? This capstone analyzes over 250,000 police dispatch incidents
and 59,000 crime reports from 2025 to identify the structural predictors of dispatch
response time and explore the relationship between crime type and dispatch behavior.

**Goals:**
- Identify what predicts dispatch response time
- Link crime type to dispatch behavior
- Build a predictive model of response time across priority levels, districts, and time of day

---

**Prerequisites**
- Python >= 3.10
- Google Colab (recommended) or Jupyter Notebook

**Required Libraries**
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn

## Running the Analysis

1. Clone this repository
2. Download `Crime.csv` and `Police_Dispatched_Incidents.csv` from the
   [Data Montgomery Open Data Portal](https://data.montgomerycountymd.gov)
   and filter both to 2025 records
3. Place raw `.csv` files in the `Data Files/` directory
4. Run notebooks in order:
   - `DATA_205_Ingestion.ipynb` — generates the three clean CSV files
   - `DATA_205_EDA.ipynb` — requires `crime_clean.csv` and `dispatch_clean.csv`
   - `DATA_205_Statistical_Tests.ipynb` — requires `dispatch_rt.csv`
   - `DATA_205_Modeling.ipynb` — requires `dispatch_rt.csv`

---

## File Descriptions

- **DATA_205_Ingestion.ipynb:** Loads raw data, standardizes columns, handles missing
  values, engineers 20+ features, applies outlier removal, and saves three clean files
- **DATA_205_EDA.ipynb:** Response time distributions, priority and district breakdowns,
  temporal heatmaps, crime vs. dispatch volume alignment
- **DATA_205_Statistical_Tests.ipynb:** Six hypothesis tests (Kruskal-Wallis,
  Mann-Whitney U, Spearman) with effect sizes and Bonferroni-corrected post-hoc tests
- **DATA_205_Modeling.ipynb:** OLS and Random Forest on raw and log-transformed response
  time; residual diagnostics, VIF check, feature importance comparison

---

## Key Findings

- **Priority drives response time** — P0-Emergency median: 4.6 min vs. P4-Standard:
  13.6 min, nearly a 3× difference (ε²=0.104, medium effect)
- **P1-High and P2-Medium are statistically indistinguishable** (Dunn post-hoc p=1.0),
  suggesting these priority levels receive equivalent dispatch urgency in practice
- **Late night is fastest** — midnight to 5am median response: 6.5 min vs. ~9.8 min
  during daytime hours, driven by lower call volume
- **Geography matters** — Districts 3D and 6D respond fastest; differences persist
  after controlling for priority
- **Weekend has no practical effect** — only 0.67 min difference vs. weekday (negligible)
- **Type-changed incidents take 12.4 minutes longer to resolve**, signaling greater
  on-scene complexity

**Best model:** Random Forest (log target) — R²=0.124, MAE=6.80 min

---

## Implications

These findings suggest that dispatch response time is largely determined by priority
classification, geographic district, and time of day. The indistinguishability of P1
and P2 response times warrants operational review. The 59,011 calls with no recorded
officer arrival represent a population worth further study for understanding call
resolution patterns.

---
