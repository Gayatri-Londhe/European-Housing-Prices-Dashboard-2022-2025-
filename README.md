# 🏠 European Housing Prices Dashboard (2022–2025)

An interactive Tableau dashboard analysing European housing price trends across 30+ countries from Q4 2022 to Q3 2025 — covering the post-pandemic recovery and ECB rate hike cycle.

---


## 📁 Project Structure

```
european-housing-prices/
├── README.md
├── data/
│   └── european_housing_prices_clean.csv
├── workbook/
│   └── European_Housing_2022-2025.twbx
├── report/
│   └── CA1_DV_Critical_Analysis_Report.pdf
└── visuals/
    ├── dashboard_overview.png
    ├── line_chart.png
    ├── bar_chart.png
    ├── stacked_bar.png
    └── map.png
```

---

## 🗂️ Dataset

| Field | Description |
|---|---|
| `country` | European country name |
| `eu_member` | EU membership status (Yes/No) |
| `eurozone_member` | Eurozone membership status (Yes/No) |
| `quarter` | Year-Quarter (e.g. 2023-Q1) |
| `price_index` | House price index (baseline: 2015 = 100) |
| `quarterly_change_pct` | % change from previous quarter |
| `yearly_change_pct` | % change from same quarter previous year |
| `price_change_since_2015_pct` | Cumulative % change since 2015 baseline |
| `data_quality` | Completeness flag |

**Coverage:** 417 records · 30+ countries · 12 quarters (Q4 2022 – Q3 2025)  
**Source:** Eurostat House Price Index

---

## 🛠️ Data Preparation

The raw dataset was cleaned and structured in Python before importing into Tableau:

- Standardised column names for Tableau compatibility
- Reshaped from wide to long format for category-level analysis
- Added calculated `Total_Spend` equivalent fields
- Validated data completeness per country and quarter
- Flagged missing values in `data_quality` column

**Tools used:** Python (pandas), Tableau Desktop/Public

---

## 📈 Dashboard Overview

The dashboard uses a **2×2 grid layout** with four complementary views and shared filters (Quarter, EU Member, Eurozone Member, Metric Selector).

### Sheet 1 — Line Chart: Price Trajectories Over Time
Tracks quarterly price index evolution for top 10 countries. Includes a **Metric Selector** parameter to toggle between:
- Price Index
- Quarterly Change %
- Yearly Change %
- Price Change Since 2015 %

### Sheet 2 — Horizontal Bar: Top 15 Countries by Avg Yearly Growth
Ranks countries by average yearly growth (2022–2025), colour-coded by EU membership status. Bulgaria leads at ~11.80% average yearly growth.

### Sheet 3 — Stacked Bar: EU vs Eurozone Membership Impact
Compares cumulative growth across Eurozone/non-Eurozone groups. Non-Eurozone countries (524.4) significantly outpaced Eurozone members (170.4), suggesting ECB rate hikes moderated Eurozone markets.

### Sheet 4 — Map: Geographic Growth Hotspots
Filled map showing average yearly growth by country, revealing a clear **East–West divide** with Eastern Europe (Bulgaria, Croatia, Czechia, Romania) showing the darkest concentration.

---

## 🔍 Key Findings

- **Eastern Europe dominates:** Bulgaria (#1 at 11.80%), Croatia, Cyprus, and Czechia lead growth rankings — reflecting economic convergence effects and lower starting price points
- **Non-Eurozone advantage:** Countries outside the Eurozone grew ~3× faster cumulatively, likely due to monetary policy flexibility during ECB's aggressive 2022–23 rate hike cycle
- **Steady but volatile uptrend:** Top performers grew from index ~900–1000 (Q4 2022) to ~1600–1800 (Q3 2025), with dips visible during peak rate shock periods (2023 Q2–Q3)
- **Geographic clustering:** Eastern Europe's spatial concentration of high growth suggests regional economic spillover effects between neighbouring markets

---

## ⚠️ Limitations

- 3-year window too short to distinguish cyclical peaks from structural trends
- National averages mask capital city vs. rural disparities
- No supply-side data (construction rates, housing stock)
- Equal country weighting (Germany = Estonia) may overstate small-market impacts
- Missing data gaps in map view not explicitly documented

---

## 🚀 Future Enhancements

- Extend to 15+ years for full housing cycle context
- Add sub-national breakdowns (capital cities vs. regions)
- Incorporate mortgage rate and income data
- Apply GDP/population weighting for economic relevance
- Add statistical significance testing

---

## 👩‍💻 About

**Gayatri Shashikant Londhe**  


[![LinkedIn](#)](https://linkedin.com) · [![Tableau Public](#)](https://public.tableau.com)
