# Crypto Market Data Cleaning

Notebook for cleaning and exploring historical Bitcoin market data.

Open `crypto_data_cleaning.ipynb` in Jupyter from this directory. The notebook expects `crypto_data.csv` alongside it. It checks data quality, parses timestamps, removes duplicate rows, forward-fills missing values, then calculates daily percentage returns, a 7-observation moving average and rolling return volatility.

The dataset source is still a placeholder in the notebook. Add the source URL and license before sharing numeric results. This is a historical-data analysis, not a real-time price tracker or investment recommendation.

Install the main dependencies from the repository root with `python -m pip install pandas numpy matplotlib requests notebook`.
