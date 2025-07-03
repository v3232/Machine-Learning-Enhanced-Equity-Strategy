# Quantitative Trading Strategy Simulation on PLTR using Machine Learning

This project builds a **machine learning-based trading system** using historical price data of **Palantir Technologies (PLTR)**. The strategy uses a **technical indicator-driven signal (EMA crossover)** and compares the performance of multiple models under **realistic trading conditions**, including **transaction costs and slippage**.

---

## Strategy Overview

The trading strategy is based on the **Exponential Moving Average Crossover** technique:

- **Buy Signal (Target = 1):** When the 20-period EMA of the closing price crosses **above** the 50-period EMA  
- **Sell Signal (Target = 0):** When the 20-period EMA crosses **below** the 50-period EMA

This crossover captures short-term momentum shifts and is commonly used in trend-following systems.

The signal is combined with other indicators like **RSI (Relative Strength Index)** and **ATR (Average True Range)** to form a feature set used for classification by machine learning models.

---

## Key Features

### Technical Indicators Engineered

- **EMA-20 and EMA-50:** For detecting short-term trend shifts  
- **RSI (14):** To gauge momentum and potential overbought/oversold conditions  
- **ATR (14):** To capture market volatility

---

## Machine Learning Models Used

All models are trained on engineered features (scaled + PCA-reduced):

- **Gradient Boosting Classifier**
- **Support Vector Machine (Linear Kernel)**
- **Logistic Regression**
- **LSTM Neural Network** (deep learning for time series patterns)

---

## Realistic Backtesting Assumptions

The backtest simulates trading from model predictions, incorporating real-world trading friction:

- **Initial Capital:** $100,000  
- **Transaction Cost:** 0.15% per trade (round trip = 0.3%)  
- **Slippage:** 0.05% price impact on each trade execution  
- **Hourly Interval:** Based on 2 years of hourly PLTR data

## Strategy Workflow
1. Data Collection: PLTR hourly OHLCV data via yfinance

2. Feature Engineering: EMA crossover + RSI + ATR

3. Labeling: Target = 1 if EMA20 > EMA50, else 0

4. Train/Test Split: 70/30, no shuffling (to preserve time order)

5. Scaling & PCA: StandardScaler + PCA (5 components)

6. Model Training & Prediction

7. Backtesting & Performance Evaluation

8. Metrics Comparison across all models

## Performance Metrics Computed
For each model, the following are tracked:

* Annualized Returns
* Cumulative Returns
* Annualized Volatility
* Sharpe Ratio
* Sortino Ratio
* Trade-by-trade Profit/Loss

## Model Comparison Snapshot
comparison table
buy sell and plots


## Tech Stack
```Python```, ```Pandas```, ```NumPy```

```scikit-learn```, ```Keras```, ```TensorFlow```

```yfinance```, ```hvPlot```

```StandardScaler```, ```PCA```, ```LSTM```, ```GradientBoosting```