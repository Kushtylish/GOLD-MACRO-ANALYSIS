# Gold & Macroeconomic Factors: A Quantitative Analysis

 ## Project Overview
This project explores the relationship between gold returns and key macroeconomic variables (inflation, interest rates, dollar index, oil, S&P 500) from 1970 to 2025. The goal is to understand gold's behavior across different economic regimes and evaluate its role as a hedge and diversifier.

## Data
- **Gold prices** (annual low/high, 1970–2025)
- **U.S. Dollar Index** (1973–2025)
- **S&P 500 Index** (1970–2025)
- **Oil prices** (1970–2025)
- **U.S. Inflation Rate** (1970–2025)
- **U.S. Interest Rate** (1970–2025)

 All data were manually compiled from public sources.

## Methodology & Findings

### 1. Exploratory Data Analysis (EDA)
- Time series plots reveal extreme volatility in gold during the 1970s and 2008–2011, and oil spikes in 2008 and 2020.
- Summary statistics: Gold average annual return ~10.8%, volatility ~23.7%; S&P 500 ~9.2% return, volatility ~13.7%.
- Outliers: 1979–1980 gold rally, 2008 financial crisis, 2020 oil negative prices.

### 2. Correlation Analysis
- Full‑period correlation matrix shows a modest positive correlation between gold and inflation (0.27, p<0.01), supporting its inflation‑hedging role.
- Gold vs. dollar index negative but not significant over the full period.
- Rolling correlations reveal that the gold‑inflation relationship was strongest in the 1970s and after 2008, but weakened during the 1990s.

### 3. Regression Analysis
- Simple OLS: gold returns are positively related to inflation (coefficient ~1.5, p<0.05) and weakly to interest rates.
- Multiple regression with inflation + interest rates: inflation remains significant; interest rates lose significance due to multicollinearity.
- Extended model with dollar index and oil: dollar index shows a significant negative coefficient (as expected), oil not significant.

### 4. Risk Metrics
- Gold: volatility 23.7%, max drawdown -51% (from 1980 peak), Sharpe ratio 0.46.
- S&P 500: Sharpe ratio 0.67, higher risk‑adjusted return over the period.
- Value at Risk (95% historical): Gold -25.2%, S&P -24.7%.

### 5. Portfolio Construction
- Minimum variance portfolio weights: Gold 8%, S&P 73%, Oil 19%, DXY 0%.
- Tangency portfolio (max Sharpe): Gold 39%, S&P 45%, Oil 0%, DXY 16% (Sharpe 0.68).
- Out‑of‑sample backtesting shows that regularisation and covariance shrinkage improve stability.

### 6. Macro Hedge Analysis
- High inflation (>3%) environments: gold returns are significantly higher (15.7% vs 7.3% in low inflation).
- Rising rates environments: gold returns slightly negative, but not statistically significant.
- Combined high‑inflation & rising‑rates: gold outperforms other assets.

### 7. Time Series Models
- ARIMA(1,0,0) forecasts gold returns with wide confidence intervals.
- VAR model shows that inflation shocks have a positive but delayed effect on gold.
- GARCH(1,1) reveals volatility clustering, with high persistence (α+β ~0.98).

### 8. Markov Switching Regimes
- Two regimes identified: low‑volatility (mean return 4.2%, volatility 12.5%) and high‑volatility (mean return 15.8%, volatility 32.1%).
- High‑volatility regime probabilities spike during the 1970s, 2008, and 2020.

### 9. Trading Strategy Backtest
- Simple rule: buy gold if last year’s inflation > 3%, else hold cash.
- Including transaction costs (0.1%), the strategy modestly outperforms buy‑and‑hold in terms of Sharpe ratio, but total return is lower.

### 10. Factor Modeling
- Macro factor model: gold returns are explained by inflation (β=1.2, p=0.04), dollar index (β=-0.3, p=0.01), and interest rates (not significant).
- The model explains ~15% of gold return variation.

### 11. Cointegration Analysis
- Gold and oil prices are cointegrated (p-value 0.03), suggesting a long‑run relationship.
- The spread is mean‑reverting, which could be used for pairs trading.

### 12. Machine Learning (Lasso & Random Forest)
- Lasso selects inflation and dollar index as the most important predictors.
- Random Forest also identifies inflation and dollar index as top features.
- Both models show modest out‑of‑sample predictive power (MSE ~200) but are limited by small sample size.

### 13. Summary & Conclusion
Gold demonstrates some inflation‑hedging properties, especially in high‑inflation environments. Its relationship with interest rates is less clear due to multicollinearity. The dollar index consistently exerts a negative influence. Risk‑adjusted returns are moderate, and gold can be a diversifier in portfolios. The macro regime matters: gold performs best when inflation is high and rates are rising. Machine learning and time series models add insight but require more data for robust forecasting.

## Technologies Used

- Python 3.10
  
**Core Data & Visualization**

pandas – data manipulation and analysis

numpy – numerical operations

matplotlib.pyplot – plotting

seaborn – enhanced statistical visualizations

**Statistical & Econometric Models**

scipy.stats – statistical tests (t‑test, Pearson correlation, etc.)

statsmodels.api – OLS regression, ARIMA, VAR, etc.

statsmodels.tsa.stattools – ADF test, cointegration, ACF/PACF

statsmodels.tsa.arima.model – ARIMA model

statsmodels.tsa.regime_switching.markov_regression – Markov switching models

statsmodels.graphics.tsaplots – ACF/PACF plots

statsmodels.stats.api – diagnostic tests (Breusch‑Pagan)

statsmodels.stats.outliers_influence – variance inflation factor (VIF)

**Financial & Time Series**

arch – GARCH models (volatility)

**Portfolio Optimization & Machine Learning**

scipy.optimize.minimize – portfolio weight optimization

sklearn.linear_model – LassoCV (regularized regression)

sklearn.ensemble – RandomForestRegressor

sklearn.preprocessing – StandardScaler

sklearn.model_selection – TimeSeriesSplit

sklearn.metrics – mean_squared_error

**Utilities**

warnings – suppress warnings (optional)

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/kushtylish/gold-macro-analysis.git
   cd gold-macro-analysis
2. Install dependencies
   ```bash
   pip install -r Requirements.txt 
3. Launch the Notebook
   ```bash
   Gold_Macro_Analysis/gold_analysis.ipynb
