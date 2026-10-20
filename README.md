# Crypto Market Data Cleaning & Analysis

This is a notebook-based analysis of historical Bitcoin market data. It uses a CSV dataset and pandas to clean timestamps and duplicate rows, calculate daily returns, a 7-day moving average and rolling volatility, and plot the price and return series.

> **Scope:** The checked-in work is a historical-data notebook. It does not currently implement a real-time API client, multi-coin dashboard, CLI, alerts, or portfolio tracking. The source of the CSV dataset should be documented before presenting numeric findings; the notebook still contains a source placeholder.

## Repository layout

```text
crypto-analysis/
├── README.md
└── Crypto-Data-minor-project-main/
    └── Crypto-Data-minor-project-main/
        ├── README.md
        ├── crypto_data.csv
        └── crypto_data_cleaning.ipynb
```

## Analysis steps

1. Load the CSV file with pandas.
2. Inspect data types, missing values and duplicate rows.
3. Parse `snapped_at` as a datetime index and remove duplicate timestamps/rows.
4. Forward-fill missing values, as currently implemented in the notebook.
5. Calculate percentage daily returns, a 7-observation moving average and rolling standard deviation of returns.
6. Plot price with the moving average and visualize daily returns.

The moving average and volatility windows are measured in rows/observations. If the source data has missing dates or irregular sampling, validate the time intervals before interpreting them as calendar-day metrics.

## Run locally

Requirements: Python 3.10+.

```bash
python -m venv .venv
```

Activate the environment:

```bash
# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS/Linux
source .venv/bin/activate
```

Install notebook dependencies and open the notebook from its data directory:

```bash
python -m pip install pandas numpy matplotlib requests notebook
cd Crypto-Data-minor-project-main/Crypto-Data-minor-project-main
jupyter notebook crypto_data_cleaning.ipynb
```

Run the cells from top to bottom. The notebook expects `crypto_data.csv` in the same working directory.

## Before using this as an analysis portfolio

- Add the real dataset source URL and license in this README.
- Report row counts, date coverage, missing-value counts and duplicates before/after cleaning.
- Avoid filling all missing values forward without checking what caused the gaps.
- State the actual date frequency and explain how return/volatility values are calculated.
- Do not frame the charts as investment advice or predictive signals.
