# Efficient Portfolio Calculator

A Python tool that identifies the optimal two-stock portfolio from any stock universe using Modern Portfolio Theory. Pass in an index name (`'NASDAQ100'`, `'SP500'`, `'FTSE100'`) or a custom list of tickers and the tool does the rest.

---

## Overview

This project uses a two-stage methodology to construct the optimal two-stock portfolio:

1. Correlation screening to identify the lowest-correlation pair across the universe
2. Mean-variance optimisation to maximise the Sharpe ratio across the efficient frontier

---

## Usage

```python
# Use a major index
portfolio_optimiser('NASDAQ100')
portfolio_optimiser('SP500')
portfolio_optimiser('FTSE100')

# Use a custom list
portfolio_optimiser(['AAPL', 'NVDA', 'AMD', 'MSFT', 'GOOGL'])
```

---

## Methodology

### Stage 1 — Correlation screening

Pulls two years of historical price data via yfinance and computes a pairwise correlation matrix across the stock universe. The lowest-correlation pair is selected to maximise diversification benefit.

### Stage 2 — Portfolio optimisation

Iterates across all possible weightings from 0% to 100% in 1% increments. For each weighting, calculates annualised portfolio return, variance, and Sharpe ratio using the two-asset variance formula. The tangency portfolio — maximum Sharpe ratio — is identified and plotted on the efficient frontier.

The risk-free rate is pulled live from yfinance using the 10-year US Treasury yield (`^TNX`).

---

## Key concepts

- Modern Portfolio Theory (Markowitz, 1952)
- Efficient frontier construction
- Sharpe ratio as the slope of the Capital Market Line
- Two-asset variance: covariance drives optimisation, correlation drives screening

---

## Tech stack

- Python
- pandas, numpy
- yfinance
- matplotlib

---

## Disclaimer

Built for educational and portfolio purposes. Not financial advice.
