---
title: Stock Market Prediction with LSTM
layout: default
---

# Stock Market Prediction using LSTM

[View Code on GitHub](https://github.com/freakingdark/Stock_market_prediction_ML_model)

---

## Project Overview

This project implements a **multi-feature LSTM deep learning model** to predict **next-day log returns of the NIFTY Bank Index (^NSEBANK)** using historical price data and technical indicators.

The model learns temporal relationships in financial time series using **sequence modeling with Long Short-Term Memory (LSTM) networks**.

Dataset period:

2008 – 2024

Sequence length:

60 trading days

Train / Validation / Test split:

- Train: 70%
- Validation: 10%
- Test: 20%

---

## Dataset and Features

### Raw Market Data

- Open  
- High  
- Low  
- Close  
- Volume  

### Technical Indicators

- RSI (14)
- MACD
- MACD Signal
- ATR
- EMA (12)
- EMA (26)
- EMA difference
- High–Low percentage
- Daily percentage change
- Momentum (1-day)
- Momentum (5-day)

### Target Variable

The model predicts **next-day log return**:
target_return = log(Close(t+1) / Close(t))


Using log returns improves numerical stability and makes the model more robust.

---

## Data Pipeline

The project follows a structured time-series ML workflow:

1. Download historical price data using **yfinance**
2. Compute technical indicators with **ta library**
3. Handle missing values
4. Perform **chronological dataset split**
5. Scale features using **MinMaxScaler**
6. Create rolling sequences of **60 time steps**
7. Train LSTM model on multivariate sequences

This prevents **data leakage** and ensures realistic financial modeling.

---

## Model Architecture

The deep learning model is implemented using **TensorFlow/Keras**.

Architecture:

- LSTM (128 units, return_sequences=True)
- Dropout (0.2)
- LSTM (64 units)
- Batch Normalization
- Dropout (0.2)
- Dense (32, ReLU)
- Dense (1, Linear)

Loss Function

Mean Squared Error (MSE)

Optimizer

Adam

Training callbacks:

- EarlyStopping
- ReduceLROnPlateau
- ModelCheckpoint

---

## Evaluation Metrics

The model is evaluated using:

- RMSE (log return prediction)
- Directional Accuracy
- Price reconstruction

Predicted closing price is reconstructed as:
predicted_price = base_price * exp(predicted_log_return)


---

## Visualizations

### Historical Price

<img src="{{ '/assets/img/banknifty_price.png' | relative_url }}" width="650">

### Technical Indicators (RSI & MACD)

<img src="{{ '/assets/img/rsi_macd.png' | relative_url }}" width="650">

### Feature Correlation

<img src="{{ '/assets/img/feature_correlation.png' | relative_url }}" width="650">

### Training Loss

<img src="{{ '/assets/img/lstm_training_loss.png' | relative_url }}" width="650">

### True vs Predicted Price

<img src="{{ '/assets/img/lstm_prediction.png' | relative_url }}" width="650">

---

## Key Machine Learning Concepts

This project demonstrates several important ML techniques:

- Multivariate time-series modeling
- Deep learning for financial forecasting
- Feature engineering using technical indicators
- Sequence modeling with LSTM
- Overfitting control using dropout and early stopping
- Learning rate scheduling
- Log-return modeling
- Price reconstruction from predicted returns

---

## Technologies Used

Python  
Pandas  
NumPy  
TensorFlow / Keras  
Scikit-learn  
Matplotlib  
Seaborn  
yfinance  
ta (technical indicators)

---

## Author

Deepali Pandey  
Data Analyst | Machine Learning | Python
