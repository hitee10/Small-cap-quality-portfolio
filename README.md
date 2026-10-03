# Small-Cap Quality Portfolio

*FINA 6334 — Empirical Methods, Northeastern University*

A systematic long-only equity strategy that isolates and exploits the **quality factor** in small-cap U.S. stocks, built on institutional-grade CRSP/Compustat data.

## Overview

This project constructs and evaluates a small-cap quality equity portfolio, grounded in the **quality-minus-junk (QMJ) framework** of Asness, Frazzini & Pedersen (2014).

**Quality definition:** stocks are scored cross-sectionally each quarter on three dimensions:
- **Gross profitability** (ROA)
- **Low accruals** (earnings quality)
- **Low leverage** (balance sheet safety)

**Universe:** U.S. common stocks, NYSE 20th–50th market-cap percentile, price ≥ $5
**Sample:** 2001–2024 (24 years)
**Rebalancing:** Quarterly, top quality quintile, 200-stock cap, equal-weighted
**Benchmark:** IWM (iShares Russell 2000 ETF)

## Methodology

- Sourced and merged institutional data from **CRSP, Compustat, and the CRSP/Compustat linking table via WRDS**
- Built quarterly cross-sectional quality scores with look-ahead bias correction
- Constructed an equal-weighted long portfolio from the top quality quintile each quarter
- Ran **Fama-French 3-factor regressions** on both the long portfolio and a long-short (Q4–Q0) spread to isolate alpha and measure factor loadings
- Conducted stress-period analysis across major market crises and tracked quarterly portfolio turnover

## Key Results

| Metric | Quality Portfolio | Benchmark (IWM) |
|---|---|---|
| Annualized Excess Return | **20.27%** | 8.15% |
| Annualized Std. Dev. | — | — |
| Sharpe Ratio | **0.946** | 0.407 |
| 3-Factor Alpha (annualized) | **9.66%** (t-stat = 8.74) | -1.46% (t-stat = -2.80) |

The portfolio's 3-factor alpha is highly statistically significant, indicating the quality signal generates returns well beyond what market, size, and value exposure explain. Average quarterly turnover was **23.2%**.

## Tools & Libraries

`Python` · `pandas` · `NumPy` · `statsmodels` · `matplotlib`

## Key Topics

Factor investing, quality signals, portfolio construction, Fama-French attribution, drawdown analysis, look-ahead bias correction
