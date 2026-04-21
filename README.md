# \# Stock Price Direction Predictor

# &#x20;

# > Predicts next-day price direction (up/down) for S\&P 500 stocks using LSTM and XGBoost on 5 years of historical data. Achieved \*\*61% directional accuracy\*\* vs. 54% naive baseline, with a simulated Sharpe ratio of \*\*1.2\*\* on a held-out 2023 test period.

# 

# \---

# 

# \## Motivation

# 

# \---

# 

# \##Data

# 

# \-\*\*Source:\*\* Yahoo Finance via `yfinance` (adjusted close prices, `auto\\\_adjust=True`)

# \- \*\*Tickers:\*\* AAPL, MSFT, GOOGL, JPM, SPY — 5 liquid, diverse tickers to avoid single-stock overfitting

# \- \*\*Period:\*\* January 2018 – December 2023 (6 years, \~1,500 trading days per ticker)

# \- \*\*Split:\*\* 70% train / 15% validation / 15% test — chronological, no shuffling

# 

# \---

# 

# \## Feature Engineering

# &#x20;

# All features computed \*\*within each split\*\* after the train/val/test division to prevent lookahead bias.

# 

# \---

# 

# \## Model Architecture

# &#x20;

# \### LSTM

# 

# \### XGBoost

# 

# \## Results

# &#x20;

# All metrics computed on the \*\*held-out 2023 test set\*\* — never used during training or tuning.

# 

# \### Backtest (simulated $10,000 portfolio, long-only, 2023)

# 

# \## SHAP Feature Importance

# 

# \## Limitations

# 

# This project is an academic exercise. Real-world deployment would face significant challenges:

# 

# 

# \## Project Structure

# &#x20;

# ```

# stock-predictor/

# ├── data/

# │ └── raw/ # Downloaded OHLCV CSVs (gitignored)

# ├── notebooks/

# │ ├── 01\_eda.ipynb # Exploratory data analysis

# │ ├── 02\_feature\_engineering.ipynb

# │ ├── 03\_modeling.ipynb # LSTM + XGBoost training

# │ └── 04\_explainability.ipynb # SHAP analysis

# ├── src/

# │ ├── data\_loader.py # yfinance download + cleaning

# │ ├── features.py # Feature engineering pipeline

# │ ├── models/

# │ │ ├── lstm.py

# │ │ └── xgboost\_model.py

# │ ├── backtest.py # Portfolio simulation

# │ └── evaluate.py # Metrics + SHAP

# ├── app.py # Streamlit demo

# ├── requirements.txt

# └── README.md

# ```

# 

# \---

# 

# \## Setup \& Usage

# 

# ```bash

# \# Clone the repo

# git clone https://github.com/yourusername/stock-predictor.git

# cd stock-predictor

# &#x20;

# \# Install dependencies

# pip install -r requirements.txt

# &#x20;

# \# Download data

# python src/data\_loader.py --tickers AAPL MSFT GOOGL JPM SPY --start 2018-01-01

# &#x20;

# \# Run full pipeline

# python src/train.py --model lstm

# &#x20;

# \# Launch demo app

# streamlit run app.py

# ```

# &#x20;

# \---

# &#x20;

# \## Tech Stack

# &#x20;

# `Python 3.10` · `PyTorch` · `XGBoost` · `scikit-learn` · `pandas` · `yfinance` · `SHAP` · `optuna` · `Streamlit`

# &#x20;

# \---

# 

# \## What I'd Do Next

# 

# \## Resume Bullet

# &#x20;

# > Engineered a time-series forecasting pipeline on 5 years of S\&P 500 data using LSTM and XGBoost.

# 

# \---

# 

# \##Legal

# 

# \*Built as a portfolio project. Not financial advice.\*

# 

# \##Checkpoint1

# &#x20;

# 

# 

# 

# 

# 

# 

# 

