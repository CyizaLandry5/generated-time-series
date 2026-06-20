# Week 1: Working with Time Series

## Course Information
- **Course:** Course 4 - Natural Language Processing (Sequence Models)
- **Platform:** DeepLearning.AI
- **Assignment:** Week 1 - Working with Time Series

## 📌 Overview
This assignment introduced the fundamentals of **time series analysis** and **forecasting**. Using synthetic data that mimics real-world time series (with trend, seasonality, and noise), I implemented various forecasting techniques and evaluated their performance using standard metrics.

The goal was to understand how to split time series data, create forecasts using different methods, and measure forecast accuracy using Mean Squared Error (MSE) and Mean Absolute Error (MAE).

## 🎯 What I Learned
- **Time Series Components:** Understood and worked with trend, seasonality, and noise in time series data.
- **Data Splitting:** Implemented a function to split time series data into training and validation sets based on a specified split point.
- **Evaluation Metrics:** Used TensorFlow's loss functions to compute MSE and MAE for forecast evaluation.
- **Naive Forecasting:** Implemented the simplest forecasting method - predicting the next value as the previous value (lag-1 forecast).
- **Moving Average:** Computed rolling mean forecasts to smooth out short-term fluctuations.
- **Differencing:** Removed seasonality and trend by subtracting values from the previous seasonal cycle (t - 365).
- **Combining Techniques:** Combined differencing with moving averages and smoothed past values to improve forecast accuracy.
- **Visualization:** Plotted time series and forecasts to visually assess performance.

## ⚙️ Key Skills Practiced
- Time series data generation and manipulation
- Train/validation splitting for time series
- Forecast evaluation with MSE and MAE
- Naive forecasting (persistence model)
- Moving average forecasting
- Seasonal differencing
- Forecast combination techniques
- Time series visualization with matplotlib

