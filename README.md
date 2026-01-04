# ⚡ Dynamics of the German Electricity Market (2019–2024)

### An Analysis of Price Volatility, Renewable Integration, and the "Merit Order" Effect

![Status](https://img.shields.io/badge/Status-Completed-success) ![Python](https://img.shields.io/badge/Python-3.11-blue) ![Tableau](https://img.shields.io/badge/Tool-Tableau-orange)

## 📌 Project Overview
This project analyzes the structural shifts in the German wholesale electricity market during the energy transition (*Energiewende*). Using 5 years of daily data from the **SMARD Platform (Bundesnetzagentur)**, I investigate how the interplay between renewable penetration and residual load drives price formation and volatility.

The analysis is particularly relevant for understanding the **2022 Energy Crisis**, separating fundamental grid drivers from external fuel-cost shocks.

---

## 📊 Key Analytical Findings

### 1. The "Hockey Stick" Supply Curve
Analysis of price spikes confirms a non-linear sensitivity to load.
* **Finding:** Residual Load is, on average, only **18.79% higher** during price spikes (972 GWh vs 818 GWh).
* **Implication:** The fact that a <20% increase in load triggers >300% price increases demonstrates the convexity of the supply curve. Once base load is exceeded, the marginal cost of backup capacity (Gas/Coal) rises exponentially.

### 2. The Merit Order Effect (Distorted)
* **Correlation:** Renewable generation has a moderate negative correlation with price (**-0.31**).
* **Observation:** While renewables generally suppress prices, the 2022 crisis decoupled this relationship. High gas prices shifted the intercept of the supply curve, causing high prices even on days with significant wind/solar output.

### 3. Volatility is Systemic, Not Just "Green"
* **Hypothesis:** Does high renewable penetration (>70%) destabilize prices?
* **Result:** Binned volatility analysis shows that price variance is **spread across all levels of renewable share**.
* **Conclusion:** Market risk in Germany is currently driven more by **Global Commodity Prices (Gas/CO2)** than by the technical intermittency of renewables.

---

## 🛠️ Repository Structure

```bash
germany-electricity-market/
├── data/
│   ├── raw/        # Original SMARD datasets
│   └── processed/  # Enriched CSVs (with volatility metrics)
├── notebooks/
│   ├── 01_data_ingestion.ipynb   # Cleaning & Time-series Alignment
│   ├── 02_eda.ipynb              # Merit Order & Correlation Analysis
│   └── 03_volatility.ipynb       # Spike Anatomy & Risk Regimes
├── tableau/
│   └── Germany_Analysis.twbx     # Interactive Dashboard
└── README.md
```

## 🚀 Technical Approach
1.  **Data Engineering:** Built a robust ETL pipeline in Python to merge disparate time-series (Consumption, Generation, Price) and handle German number formatting.
2.  **Statistical Testing:** Used **Mann-Whitney U Tests** to prove that load differences during price spikes were statistically significant ( < 0.05$).
3.  **Visualization:** Designed Tableau dashboards to allow stakeholders to filter market regimes by year (Pre-Crisis vs. Crisis).

## 📥 Getting Started
1.  Clone the repo:
    `git clone https://github.com/your-username/germany-electricity-market.git`
2.  Install dependencies:
    `pip install -r requirements.txt`
3.  Run the notebooks in order (01 -> 02 -> 03).

## 📊 Interactive Dashboards
The static images below are just previews. **[Click here to explore the full interactive dashboards on Tableau Public.](https://public.tableau.com/app/profile/gaurav.hada/viz/germany_electricity_market_analysis/SystemOverview?publish=yes)**

[![Dashboard Preview](https://github.com/user-attachments/assets/d5a712c2-d6b4-4e7b-985e-a917c0fe4067)](https://public.tableau.com/app/profile/gaurav.hada/viz/germany_electricity_market_analysis/SystemOverview?publish=yes)

*Tip: Use the tabs at the top of the Tableau visualization to navigate between "System Overview", "Price Drivers", and "Volatility Analysis".*

## 📬 Contact
* **Author:** Gaurav Hada
* **Data Source:** [SMARD.de](https://www.smard.de/en)