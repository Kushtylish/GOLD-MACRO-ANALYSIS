# Gold & Macroeconomic Factors: A Quantitative Analysis

## 📌 Project Overview
This project explores the relationship between gold returns and key macroeconomic variables – inflation, interest rates, the U.S. Dollar Index, S&P 500, and oil prices – from 1970 to 2025. The goal is to understand how gold behaves under different economic regimes and whether it serves as an inflation hedge.

## 📊 Data
The dataset combines annual:
- Gold prices (Low/High, from 1970–2025)
- U.S. Dollar Index (1973–2025)
- S&P 500 index (1970–2025)
- Oil prices (1970–2025)
- U.S. Inflation Rate (1970–2025)
- U.S. Interest Rate (1970–2025)

All data were manually compiled from public sources.

## 🔬 Methodology
1. **Exploratory Data Analysis** – time series plots, summary statistics, distribution checks, outlier detection.
2. **Rolling Correlations** – 5‑year rolling correlations between gold and each factor, with Fisher‑z confidence bands.
3. **Full‑Period Correlation Matrix** – heatmap with significance stars.
4. **Regression Analysis** – OLS models to quantify gold’s sensitivity to inflation and interest rates, with diagnostics (VIF, heteroskedasticity, normality of residuals).
5. **Change Point Detection** – CUSUM, CUSUMSQ, and Bayesian change point models to identify structural breaks in the gold‑inflation relationship.

## 📈 Key Findings
- Gold shows a modest positive correlation with inflation (≈0.27, p<0.01) over the full period, supporting its role as an inflation hedge.
- The relationship with interest rates is weaker and often non‑significant after controlling for inflation, due to multicollinearity.
- Rolling correlations reveal that the gold‑inflation link is not stable: it weakened during the 1990s and strengthened again after the 2008 financial crisis.
- A structural break in the gold‑inflation relationship is detected around 1980 (end of the gold standard?) and again around 2008.
- The dollar index consistently shows a negative correlation with gold, as expected.

## 🛠️ Technologies Used
- Python 3.10
- pandas, numpy, matplotlib, seaborn
- statsmodels (regression, CUSUM, VIF)
- scipy (statistical tests)
- pymc (Bayesian change point)
- ruptures (change point detection)

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/kushtylish/gold-macro-analysis.git
   cd gold-macro-analysis
2. Install dependencies
   ```bash
   git clone
   pip install -r Requirements.txt 
 
