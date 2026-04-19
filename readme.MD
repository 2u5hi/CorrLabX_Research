# Market Research: NASDAQ vs S&P 500

This project tests whether the very high correlation between NASDAQ and S&P 500 price levels is actually meaningful for market analysis and prediction.

The main conclusion is that raw price correlation is inflated by shared long-term trends. When the analysis is moved to daily returns and out-of-sample forecasting, the relationship remains strong but the predictive edge becomes weak.

## Key Results

- Raw price correlation: `0.9932`
- Daily return correlation: `0.9495`
- Rolling 90-day return correlation: `0.83` to `0.99`
- Linear regression test-set `R^2`: `0.9221`
- ARIMA directional accuracy on unseen data: `52.7%`

## Project Structure

- `data/`: input CSV files for NASDAQ and S&P 500
- `notebooks/analysis.ipynb`: full analysis notebook
- `nasdaq_sp500_analysis.png`: price and return comparison figure
- `rolling_correlation.png`: rolling-correlation figure
- `regression.png`: regression diagnostics
- `arima_forecast.png`: ARIMA forecast figure

## Methods

The notebook covers four steps:

1. Compare correlation in raw price levels versus daily returns.
2. Measure how return correlation changes over time with a 90-day rolling window.
3. Fit a linear regression model to test same-period co-movement.
4. Run ARIMA on NASDAQ returns using walk-forward validation to test real forecasting value.

## Setup

Install the required packages:

```bash
pip install -r requirements.txt
```

## Running The Analysis

Open and run [analysis.ipynb](C:\Users\dhanu\Downloads\market_research\notebooks\analysis.ipynb).

The notebook now resolves paths relative to the project, so it works whether you launch Jupyter from the repo root or from the `notebooks/` directory.

## Takeaway

Evaluated relationship between statistical correlation and predictive power in financial time series


High correlation in price levels is largely driven by shared non-stationary trends, making it misleading for inference about true co-movement or predictability.

## Conclusion
Correlation captures structural co-movement but does not imply predictive power. Proper time-series evaluation reveals that most apparent signal in raw prices is due to shared trends rather than exploitable relationships.

## Hypothesis Extension
- This motivates testing whether lower-efficiency markets (e.g., OTC equities) exhibit stronger residual predictive structure under similar modeling constraints.

## quick bullets

- Built statistical analysis pipeline comparing NASDAQ and S&P 500 using Python, pandas, and scikit-learn
- Demonstrated that raw price correlation (r = 0.9932) is inflated due to non-stationary trends
- Conducted rolling correlation analysis revealing regime-dependent market structure (0.83–0.99)
- Developed regression model explaining index co-movement with R² = 0.9221
- Implemented ARIMA forecasting model achieving 52.7% directional accuracy on unseen data
- Evaluated relationship between statistical correlation and predictive power in financial time series