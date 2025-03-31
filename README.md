---

## 📈 Project Summary

This project compares traditional and machine learning-based time series forecasting techniques for predicting short-term stock prices. Both the ARIMA model and a Gradient Boosting Regressor (GBM) were implemented and evaluated using historical OHLCV data from Yahoo Finance.

---

## 🧪 How to Run

Install dependencies:

```bash
pip install yfinance pandas numpy matplotlib scikit-learn statsmodels
then run jupyter lab

---

## 📊 Data and Feature Engineering

Daily stock data (Open, High, Low, Close, Volume) from 2019 to 2024 was collected via the yfinance API. After preprocessing and handling missing values, new features were engineered to improve model performance:

- Lagged closing prices (Lag_1, Lag_2, Lag_3)
- Moving averages (MA_5, MA_20)
- Daily returns and volatility
- Volume change ratios

These features capture both momentum and risk, which are critical in financial forecasting.

---

## 🤖 ARIMA Model Insights

ARIMA is a well-known statistical model for time series analysis. However, it often struggles with volatile financial series, especially in short-term prediction. In this study, the ARIMA(1,1,1) model produced a flat forecast that failed to react to sudden price movements. This underperformance limits its usefulness in short-term trading strategies.

---

## ⚡ Gradient Boosting Model Results

The Gradient Boosting model trained on engineered features achieved strong predictive power, with the following performance:

- **MAPE:** 9.25%  
- **MAE:** 20.87  
- **RMSE:** 29.44

This level of accuracy is considered solid, especially in financial data where noise and unpredictability are high. The model was also able to better adapt to volatility and trend shifts.

---

## 📏 ARIMA vs GBM - Comparison

| Metric | ARIMA | Gradient Boosting |
|--------|-------|-------------------|
| RMSE   | N/A   | 29.44 |
| MAE    | N/A   | 20.87 |
| MAPE   | N/A   | 9.25% |

GBM significantly outperformed ARIMA in all metrics. While ARIMA may track long-term trends, it lacks responsiveness to rapid market changes — a critical weakness for short-term forecasting.

---

## 💡 Strategic Recommendation

For short-term price forecasting, **Gradient Boosting** offers a more dynamic and reliable approach. Given its superior performance and flexibility, it is a stronger candidate for deployment in data-driven trading systems.

---

## 🚀 Next Steps

- Incorporate more stocks and macroeconomic indicators  
- Tune hyperparameters using tools like GridSearchCV or Optuna  
- Test other models like XGBoost, LightGBM, or LSTM  
- Deploy the best model into a real-time trading dashboard

## 🔬 Engineered Features

| Feature         | Description                            |
|----------------|----------------------------------------|
| Lag_1, Lag_2    | Previous day(s) closing prices         |
| MA_5, MA_20     | 5-day and 20-day moving averages       |
| Return          | Daily return (percentage change)       |
| Volatility_5    | 5-day rolling standard deviation       |
| Volume_Change   | Daily % change in volume               |

---
