# 📈 Stock Return Prediction

## 📌 Overview

This project focuses on **predicting next-day stock returns** using machine learning models and financial time-series data. The objective is to evaluate how well different models can learn patterns from historical market data and technical indicators to forecast short-term stock returns.

---

## 🎯 Problem Statement

Stock return prediction is a challenging task due to:

* High noise and volatility in financial markets
* Non-linear and non-stationary time-series behaviour
* Weak predictive signals in historical price data

This project aims to:

* Predict **next-day stock returns**
* Compare multiple machine learning approaches
* Understand how model assumptions affect performance on financial data

---

## 📊 Dataset

The dataset consists of:

Historical **stock market data** for the following assets from `2017-01-01` to `2020-12-31`:

* **JNJ (Johnson & Johnson)** – healthcare sector
* **AAPL (Apple Inc.)** – technology sector
* **MSFT (Microsoft)** – technology sector
* **PG (Procter & Gamble)** – consumer goods
* **KO (Coca-Cola)** – consumer defensive

**The S&P 500 market index data**
- The S&P 500 is a stock market index that tracks the performance of approximately 500 major U.S. companies across various industries, including technology, healthcare, and finance. It is widely regarded as the best single gauge of large-cap U.S. equities, covering about 80% of the total market capitalization of the U.S. stock market.

---

## 📈 Features

The features are designed to capture key aspects of market behaviour:

* **Trend (Moving Averages)**

  * **SMA_10** → captures short-term price movements and recent market direction
  * **SMA_50** → reflects medium-term trends and smoother price behaviour
  * **SMA_200** → identifies long-term trend and overall market direction

* **Volatility**

  * **Rolling Volatility** → measures how much prices vary over a recent period
  * **Bollinger Bands** → highlights when prices deviate significantly from their recent average
  * **ATR (Average True Range)** → captures typical price movement size to assess market risk

* **Momentum**
  
  * **RSI (Relative Strength Index)** → identifies overbought or oversold conditions
  * **MACD (Moving Average Convergence Divergence)** → detects changes in momentum and potential trend shifts

---

### Feature Selection

Feature selection is based on:

* **Feature importance analysis from Random Forest**
* **Coefficient significance analysis from OLS**

---

## ⚙️ Methodoligy

### Model Development

Three models are implemented:

* **Ordinary Least Squares (OLS)**

  * Linear baseline model

* **Support Vector Regression (SVR)**

  * Non-linear model using kernel methods

* **Random Forest (RF)**

  * Ensemble model capturing non-linear relationships and interactions

---

### Hyperparameter Tuning

* Performed using **GridSearchCV**
* Applied during model selection phase

---

## 🔄 Model Evaluation Strategy

* **Final Evaluation**

  * Performed using a **chronological train/test split**
  * Ensures the model is evaluated on **unseen future data**
  * Prevents data leakage

* **Model Selection & Robustness**

  * Conducted using **TimeSeries Cross-Validation (rolling window)**
  * Specifically designed for time-series data
  * Avoids leakage by preserving temporal order

* **Baseline Comparison**

  * Models are compared against a **mean baseline predictor** as a reference

### Evaluation Metrics

* Mean Squared Error (MSE)
* R² score
* Directional Accuracy (DA)

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Jupyter Notebook

---

## 🔮 Future Work

* Incorporating deep learning models (e.g., LSTM, GRU)
* Adding macroeconomic or sentiment data
* Improving feature selection techniques
* Exploring causal inference approaches
* Extending to portfolio-level prediction
