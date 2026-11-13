# Cross-Sectional Momentum on S&P 500

Systematic alpha research notebook testing the cross-sectional momentum factor on S&P 500 constituents (2010-2026).

## Strategy

- Rank all S&P 500 stocks by trailing 12-month log returns
- Long top decile (winners), short bottom decile (losers)
- Equal-weighted, monthly rebalancing

## Key Results

| Metric | Value |
|--------|-------|
| Annualized Return | 6.7% |
| Annualized Volatility | 21.4% |
| Sharpe Ratio | 0.314 |
| Win Rate | 54% (102/189 months) |

## Robustness Checks

- **Alpha decay**: no decay detected. Late period (2019-2026) Sharpe of 0.400 vs early period (2011-2018) Sharpe of 0.196
- **Lookback sensitivity**: 12-month lookback optimal (Sharpe 0.314), consistent with Jegadeesh & Titman (1993). 3-month too noisy (0.030), 24-month signal dies due to long-term reversal (DeBondt & Thaler, 1985)
- **12-0 vs 12-1**: skipping the most recent month does not improve performance (0.245 vs 0.314)
- **Sector analysis**: Information Technology overrepresented in the winner portfolio
- **Survivorship bias**: discussed as a key limitation. Current index composition used instead of historical constituents; reported Sharpe is an upper bound

## Data

- Source: Yahoo Finance (yfinance)
- Universe: S&P 500 current constituents (503 tickers)
- Period: January 2010 - October 2026
- Frequency: monthly (resampled from daily adjusted close)

## Tech Stack

Python, pandas, NumPy, yfinance, matplotlib

## Author

Sofian Hussein
