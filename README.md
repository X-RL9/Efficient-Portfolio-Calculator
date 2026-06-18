# Efficient Two-Stock Portfolio Optimiser

A Python implementation of Modern Portfolio Theory applied to AI and 
semiconductor equities, combining correlation screening with 
Sharpe ratio optimisation to construct the optimal two-stock portfolio.

---

## Overview

This project identifies the optimal two-stock portfolio, with an example of tech stocks (NVIDIA, AMD, TSMC, Broadcom, and others) using 
a two-stage methodology:

1. Correlation screening to identify pairs with diversification potential
2. Mean-variance optimisation to maximise the Sharpe ratio across the 
efficient frontier

---

## Methodology

### Stage 1 — Correlation screening
Pulls historical price data via yfinance and computes a correlation 
matrix across the stock universe. Pairs are screened for low or negative 
correlation to ensure genuine diversification benefit.

### Stage 2 — Portfolio optimisation
For each candidate pair, runs a Monte Carlo simulation across 10,000 
random portfolio weightings. Plots the efficient frontier and identifies 
the tangency portfolio — the allocation with the maximum Sharpe ratio.

---

## Key concepts

- Modern Portfolio Theory (Markowitz, 1952)
- Efficient frontier construction
- Sharpe ratio as the Capital Market Line slope
- Risk-return decomposition: systematic vs idiosyncratic risk

---

## Tech stack

- Python
- pandas, numpy
- yfinance
- matplotlib

---

## Disclaimer

Built for educational and portfolio purposes. Not financial advice.
