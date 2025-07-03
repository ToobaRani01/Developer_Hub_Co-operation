# Report: Stock Price Anomaly Detection

## 🔍 Overview
This project detects unusual behavior in Apple’s stock price (AAPL) from 2018 to 2023 using technical indicators and machine learning.

---

## 🧼 Data Preparation
- Loaded stock data using `yfinance` and cleaned it (removed missing/outlier values).
- Standardized features like `Open`, `High`, `Low`, `Close`, and `Volume`.

---

## 📈 Technical Indicators
Added these indicators:
- **SMA**: Simple Moving Average (20 days)
- **EMA**: Exponential Moving Average (20 days)
- **RSI**: Relative Strength Index (14 days)v\
- **Bollinger Bands**: Price range envelope

---

## ⚙️ Challenges & Model Rationale
- **Isolation Forest** was used due to its ability to flag outliers without needing labeled data.
- **LSTM** was chosen to model price trends over time and detect forecast errors.
- **Challenge:** Handling missing or inconsistent data  
  - *Solution:* Applied `.dropna()` and `StandardScaler` after type conversion.

---

## 🕵️ Anomaly Detection

### 📌 Method 1: Isolation Forest
- Used stock indicators to detect outliers.
- Anomalies shown as red points on price plot.

### 📌 Method 2: LSTM Forecasting
- Built an LSTM model to predict prices.
- Flagged anomalies where predictions differed a lot from real values.

---

## 📊 Results
- **Isolation Forest** found around 2% anomalies (mostly high/low volumes).
- **LSTM** spotted strange future patterns.

---

## ✅ Summary
By combining price trends and forecasting, this tool helps detect:
- Market manipulation
- Technical breakouts
- Unusual trading behavior