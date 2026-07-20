# 📈 Hybrid ARIMA–LSTM NIFTY 50 Prediction System

A hybrid time-series forecasting system that combines **ARIMA** and **LSTM** models to predict the **next trading day's NIFTY 50 closing price**. The project leverages ARIMA to capture linear trends and an LSTM network to model residual (non-linear) patterns, resulting in improved short-term forecasting performance. The application is deployed through a **Streamlit dashboard** for interactive visualization and prediction. :contentReference[oaicite:0]{index=0}

---

## 🚀 Features

- Hybrid forecasting using **ARIMA + LSTM**
- Predicts the **next NSE trading day's closing price**
- Automatically fetches the latest NIFTY 50 data using Yahoo Finance
- Handles weekends and NSE holidays automatically
- Interactive Streamlit dashboard
- Forecast visualization with historical closing prices
- Saved trained models for fast inference

---

## 📂 Project Structure

```
Hybrid-ARIMA-LSTM-NIFTY/
│
├── app.py                  # Streamlit Dashboard
├── training.py             # Model Training Script
├── prediction.py           # Standalone Prediction Script
│
├── arima_model.pkl         # Trained ARIMA model
├── lstm_model.h5           # Trained LSTM model
├── residual_scaler.pkl     # Residual scaler
│
├── README.md
```

---

## 🧠 Project Workflow

```
Historical NIFTY Data
          │
          ▼
 Data Preprocessing
          │
          ▼
   ARIMA Model Training
          │
          ▼
 Compute Prediction Residuals
          │
          ▼
 Scale Residuals
          │
          ▼
 Train LSTM on Residuals
          │
          ▼
Next Day Forecast
      =
ARIMA Forecast
      +
LSTM Residual Prediction
          │
          ▼
 Final Hybrid Prediction
```

---

## 📊 Technologies Used

- Python
- ARIMA (Statsmodels)
- TensorFlow / Keras
- LSTM
- Scikit-learn
- Streamlit
- Yahoo Finance API
- Matplotlib
- Pandas
- NumPy

---

## 📈 Model Architecture

### ARIMA

- Captures the linear trend of NIFTY closing prices.
- Best model selected using AIC after grid search.
- Forecasts the next closing price.

### LSTM

- Trained on ARIMA residuals.
- Learns hidden non-linear patterns.
- Predicts the next residual.

### Hybrid Forecast

```
Final Prediction
=
ARIMA Forecast
+
Predicted Residual (LSTM)
```

This combination improves prediction accuracy by utilizing the strengths of both statistical and deep learning models. :contentReference[oaicite:1]{index=1}

---

## 📅 Data Source

Historical market data is downloaded directly from **Yahoo Finance**.

Ticker:

```
^NSEI
```

Time Window:

- Last 4 Years
- Daily Closing Prices 

---

## ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/yourusername/Hybrid-ARIMA-LSTM-NIFTY.git

cd Hybrid-ARIMA-LSTM-NIFTY
```


## ▶️ Train the Model

Run

```bash
python training.py
```

This generates:

- arima_model.pkl
- lstm_model.h5
- residual_scaler.pkl 
---

## 🔮 Predict Next Trading Day

Run

```bash
python prediction.py
```

The script outputs:

- Last Trading Day
- Next Trading Day
- Previous Close
- Predicted Close
- Expected Point Change 

---

## 🌐 Run Streamlit Dashboard

```bash
streamlit run app.py
```

Dashboard includes:

- Prediction summary table
- Previous closing price
- Next predicted closing price
- Interactive forecast curve
- Past 1–4 trading day visualization

---


## 📌 Future Improvements

- Multi-day forecasting
- Transformer-based forecasting models
- Live NSE API integration
- Hyperparameter optimization using Optuna
- Docker deployment
- CI/CD pipeline
- Automated weekly model retraining
- Performance monitoring dashboard

---

## 👨‍💻 Author

**Samar Markande**

B.Tech Computer Science (Data Science)


## 📄 License

This project is intended for educational and research purposes.

```


