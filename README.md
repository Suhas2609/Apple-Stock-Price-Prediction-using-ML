# Apple Stock Price Prediction using News Sentiment & Technical Indicators

## 🔍 Problem Statement

Forecast future **Apple Inc. (AAPL)** stock prices using a combination of historical market data, technical indicators, and daily news sentiment analysis.

---

## 📦 Dataset Used

1. **`aapl_stock.csv`**

   * Historical price data: Open, High, Low, Close, Volume.
   * Used to derive technical indicators and lagged features.

2. **`news_for_finbert.csv`**

   * News headlines related to Apple.
   * Sentiment extracted using **FinBERT** or similar finance-specific NLP models.

---

## ⚙️ Workflow Overview

### 1. Data Cleaning & Preprocessing

* Parsed date columns and synchronized across datasets.
* Cleaned stock data and ensured consistent formats.
* Converted news `datetime` into daily granularity.

### 2. Sentiment Extraction

* Used FinBERT or similar transformer model for extracting sentiment from headlines.
* Aggregated average sentiment **per day**.

### 3. Feature Engineering

#### a. Lagged Features

* Created lag variables: `Close_Lag1`, `Close_Lag2`, ..., `Close_Lag5`
* Captures autocorrelation and historical dependencies

#### b. Technical Indicators

* **RSI** (Relative Strength Index)
* **MACD** (Moving Average Convergence Divergence)
* **OBV** (On-Balance Volume)
* **ATR** (Average True Range)
* **Bollinger Bands** (Upper & Lower bounds)

#### c. Merge Data

* Merged sentiment and technical features on daily basis
* Final dataset combined prices, sentiment, and indicators

---

## 📊 Exploratory Data Analysis (EDA)

* **Correlation Heatmaps**:

  * Lagged Close prices showed strong autocorrelation (\~0.99)
  * Technical indicators correlated moderately (0.6-0.8)
  * Sentiment had weak direct correlation (<0.05)

* **Inferences**:

  * Sentiment may offer nonlinear effects not captured in correlation
  * Lagged features are powerful predictors for sequential models

---

## 📊 Modeling Plan

*While modeling was prepared, this notebook focuses on data preparation and insight extraction.*

### Planned Models

* **LSTM**: Sequential learning with time dependencies
* **Transformer**: Attention-based architecture for multivariate time series
* **Hybrid**: Combine numerical + NLP sentiment embeddings

---

## 🧠 Learnings

* News sentiment needs careful alignment and context treatment.
* Technical indicators + lagged prices form a strong base signal.
* Visual correlation doesn't always reflect nonlinear relationships (especially for NLP features).

---

## 🚀 Future Enhancements

* Train and compare **LSTM vs Transformer** models
* Improve sentiment quality with better NLP models or multiple headlines per day
* Explore volatility prediction (e.g., for options trading)

---

## 📁 Folder Structure (Suggested)

```
AAPL_Price_Prediction/
├── aapl1.ipynb
├── README.md
```

---

## 📈 Tools & Libraries

* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `sklearn` for preprocessing
* `ta-lib` or `pandas-ta` for technical indicators
* FinBERT (HuggingFace Transformers)
* Future use of TensorFlow / PyTorch for LSTM/Transformer models

---

## 📅 Timeline Summary

* Data Cleaning & Syncing ✅
* Sentiment Aggregation ✅
* Technical Indicator Engineering ✅
* Feature Merging & EDA ✅
* Modeling Plan (Outlined) ✅
