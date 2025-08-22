## Forecasting Agricultural Commodity Prices Using Time Series and Deep Learning Models

This project focuses on forecasting the prices of agricultural commodities (specifically wheat) using both classical time series models and deep learning approaches. The aim is to explore how different modeling techniques perform under varying data resolutions and input features.

# 🔍 Objectives:
- Forecast monthly wheat prices using SARIMAX with exogenous factors (rainfall, inflation).
- Forecast monthly wheat prices using a Recurrent Neural Network (RNN) model with the same exogenous inputs.
- Forecast daily wheat prices using an RNN model without external inputs.
- Compare the models based on forecast accuracy and behavior over time.
- Forecasting Agricultural Commodity Prices Using Time Series and Deep Learning Models


# 📁 Dataset Overview:
- Monthly data (wheat.csv): includes PRICE, RAINFALL, and INFLATION from Jan 2001 to Dec 2024.
- Daily data (wheatdaily.csv): includes PRICE from Jan 2014 to Sep 2025 (interpolated for missing dates).

📈 Part A – SARIMAX Model (Monthly Data with Rainfall & Inflation)
In this section, we use the SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors) model to forecast monthly wheat prices. The model incorporates external factors like rainfall and inflation to improve forecast accuracy.

# Key Features:

- Input: Monthly PRICE, RAINFALL, INFLATION
- Forecast Range: 2025–2027
- Output: Forecast with 95% Confidence Intervals

# 🤖 Part B – RNN Model (Monthly Data with Rainfall & Inflation)
This section implements a Recurrent Neural Network (RNN) using Keras to model and forecast monthly wheat prices. It uses the same inputs as the SARIMAX model, allowing for a direct performance comparison between classical and deep learning methods.

# Key Features:

- Input: Monthly PRICE, RAINFALL, INFLATION (scaled)
- Model: Simple RNN with sliding window (12 months)
- Forecast Horizon: 2025–2027

# 📅 Part C – RNN Model (Daily Price Only, No Exogenous Variables)
This section trains a daily price forecasting model using an RNN. Unlike the previous models, it does not use any external variables. It focuses on capturing short-term temporal dependencies in the daily price movement.

# Key Features:

- Input: Daily PRICE only
- Forecast Horizon: Next 3 years (1095 days)
- Output: Detailed forecast of daily price trends

# 📊 Model Evaluation and Comparison
Here, we compare the performance of all three models using metrics like RMSE (Root Mean Squared Error) on test data, visual inspection of forecasts, and model interpretability.

# Model	Data Type	Exogenous	RMSE	Notes
- SARIMAX	Monthly	Yes	2586.95	Traditional, interpretable
 -RNN (Monthly)	Monthly	Yes	79.64	Deep learning with externals
- RNN (Daily)	Daily	No	0.66	Captures short-term trends
# 🧾 Conclusion
This project explored multiple approaches to forecast wheat prices:

- Classical SARIMAX model showed strong performance with interpretable confidence intervals.
- RNN with monthly data captured non-linear patterns and exogenous effects, offering a flexible deep learning alternative.
- RNN with daily data, while limited to price-only input, demonstrated fine-grained trends over short time frames.
# Future Work:
- Try LSTM or GRU models for deeper temporal learning
- Experiment with different exogenous variables (e.g., NDVI, global oil prices)
- Introduce attention mechanisms for better sequence weighting
