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

## 🚧 Challenges Faced
1. **Understanding Time Series Components:** Distinguishing between trend, seasonality, and noise in the generated data.
2. **Naive Forecast Slicing:** Correctly shifting the series by one time step while matching the validation period length.
3. **Moving Average Implementation:** Computing the rolling mean without using built-in pandas functions, using a loop over the series.
4. **Differencing Logic:** Understanding why subtracting t-365 values removes both trend and seasonality (seasonal period = 365 days).
5. **Index Slicing for Differencing:** Ensuring `diff_series` had the correct length (`len(SERIES) - 365`) and that `diff_time` matched appropriately.
6. **Forecast Alignment:** Ensuring all forecast series matched the validation period in both length and time indices.
7. **Smoothing Past Values:** Figuring out the correct slicing for `SERIES[SPLIT_TIME - 370:-360]` to apply a moving average with window_size=11.

## 📋 Important Submission Notes (AutoGrader)
To avoid grader errors from the DeepLearning.AI AutoGrader, I made sure NOT to:
- Add any extra `print` statements in the assignment
- Add any extra code cells
- Change any of the function parameters
- Use global variables inside graded exercises (unless specifically instructed)
- Change the assignment code where not required

> 💡 **Tips:**
> - Use `# grade-up-to-here` in graded cells to check progress
> - All cells are frozen except for solution cells
> - Avoid using global variables

## 🛠️ Technologies & Tools
- Python 3
- NumPy
- TensorFlow (tf.keras.losses)
- Matplotlib
- Custom time series generation functions

## 📈 Results
### Forecast Performance Summary

| Method | MSE | MAE | Comments |
|--------|-----|-----|----------|
| **Naive Forecast** | 19.58 | 2.60 | Baseline, simple lag-1 prediction |
| **Moving Average** | 56.80 | 4.12 | Worse than naive, doesn't capture trend/seasonality |
| **Differencing + Moving Avg** | - | - | Removed trend/seasonality |
| **Diff MA + Past Values** | 8.50 | 2.33 | Added back past season values |
| **Diff MA + Smooth Past** | 13.57 | 2.26 | Smoothed version, lower MAE but higher MSE |

### Best Performing Method
**Differencing + Moving Average + Past Values** achieved the lowest MSE (8.50), while **Smoothing** achieved the lowest MAE (2.26), indicating a trade-off between bias and variance.

