# Congressional Alpha: Do U.S. Senators Trade on Inside Information?

An empirical analysis of 6,700+ disclosed U.S. Senate stock trades (2012–2024), testing whether senators earn abnormal returns and whether the public can profit by copying them.

**Short answer: No.**

## Key Findings

| Test | Result |
|------|--------|
| Insider alpha (FF3 regression) | No significant alpha at any holding period (EW or VW) |
| Replication alpha (post-disclosure) | Negative excess returns at every lag (1–60 days) |
| Persistence | Year-to-year correlation r = 0.045 (p = 0.67) — winners don't repeat |
| COVID event study | Loeffler and others traded suspiciously in early 2020, but this doesn't generalize |
| Follow-winners backtest | Strategy returns -0.6%/yr vs market's +12.1%/yr |
| Quiver Quant's headline numbers | Explained entirely by starting the backtest at the April 2020 market bottom |

The average senator underperforms the market by roughly 12 percentage points annually. Platforms selling congressional trading data are selling noise dressed up as signal.

## Analysis Structure

| Section | Description |
|---------|-------------|
| 1 | Executive Summary |
| 2 | Literature Review |
| 3 | Data and Sample Construction |
| 4 | Insider Alpha: Calendar-Time Portfolios (FF3 regressions, multiple holding periods) |
| 5 | COVID Event Study (Loeffler, Burr, Feinstein, Inhofe) |
| 6 | Persistence: Do Past Winners Predict Future Winners? |
| 7 | Replication Alpha: Can You Profit After Disclosure? |
| 8 | Robustness Checks and Outlier Analysis |
| 9 | Backtest: Follow Last Year's Winners |
| 10 | Why Does Quiver Show Something Different? |
| 11 | Conclusion |

## Data Sources

- **Trade disclosures**: [Quiver Quantitative](https://www.quiverquant.com/congresstrading/) — all disclosed Senate trades, filtered to the `Senate` sheet in `Congressional Trades.xlsx`
- **Stock returns**: CRSP daily stock file via [WRDS](https://wrds-www.wharton.upenn.edu/) (requires institutional access)
- **Risk factors**: Fama-French 3-factor daily data via WRDS
- **Ticker-PERMNO mapping**: CRSP `dsenames` table via WRDS

## Requirements

- Python 3.10+
- Jupyter Notebook
- WRDS account with access to CRSP and Fama-French databases
- Key packages: `wrds`, `pandas`, `numpy`, `statsmodels`, `scipy`, `matplotlib`

Install dependencies:

```bash
pip install wrds pandas numpy statsmodels scipy matplotlib
```

## How to Run

1. Clone this repository
2. Open `Senate Info Advantage Analysis.ipynb` in Jupyter
3. Run cells sequentially — the notebook will prompt for your WRDS credentials on first connection
4. The Excel file `Congressional Trades.xlsx` must be in the same directory as the notebook

## Files

| File | Description |
|------|-------------|
| `Senate Info Advantage Analysis.ipynb` | Full analysis notebook (66 cells) |
| `Congressional Trades.xlsx` | Raw trade disclosure data from Quiver Quant, with a `Senate` sheet filtered to Senate trades only |
| `README.md` | This file |

## License

MIT
