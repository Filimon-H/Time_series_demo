okay now give me a detailed prompt for winsudtf for me to build a demo mini project inn one notebok to explain this concepts and also to comapre them and we use from yaho finance usinf y finance to fetch the stock data and try to get one stationary data and on evolatile data to comapre

This project is a perfect way to show how "old school" statistics meets "new school" deep learning. To make the comparison fair and educational, you need two different types of data: one that is "well-behaved" (stationary) and one that is "chaotic" (volatile).

The Dataset Strategy
For your project, we will use two specific tickers from the YFinance library to represent these concepts:

Stationary/Stable Data (BND - Vanguard Total Bond Market ETF): Bonds are generally less volatile and have more predictable, mean-reverting patterns. They are excellent for testing if ARIMA can capture a steady trend.

Volatile/Non-Linear Data (TSLA - Tesla): Tesla is famous for dramatic price swings and complex patterns that don't follow a straight line. This is the ultimate "stress test" for LSTM.

Project Notebook Structure (The Prompt)
You can use the prompt below with an AI tool (like ChatGPT or Claude) or follow it manually to build your notebook.

"Create a Python Jupyter Notebook project for a time series forecasting comparison between ARIMA, SARIMA, and LSTM. Use the following specifications:"

1. Data Acquisition
Use yfinance to download historical daily closing prices from 2015-01-01 to 2025-01-15.

Target 1 (Stable): BND (Vanguard Total Bond Market ETF).

Target 2 (Volatile): TSLA (Tesla).

2. Preprocessing & EDA
Plot the data to visualize the difference in volatility.

Perform an Augmented Dickey-Fuller (ADF) test to check for stationarity.

Apply Log Transformation and Differencing to see how non-stationary data can be "tamed" for ARIMA models.

3. Modeling Phase
ARIMA Model: Use pmdarima.auto_arima to automatically find the best (p, d, q) parameters for both stocks.

SARIMA Model: Add seasonal parameters (e.g., m=5 for a 5-day trading week) to see if it improves the bond forecast.

LSTM Model: Build a Sequential model with:

2 LSTM layers (50-100 units).

Dropout layers to prevent overfitting.

A Dense output layer.

Note: Use MinMaxScaler because neural networks are sensitive to the scale of stock prices.

4. Evaluation & Comparison
Forecast the last 30 days of the dataset (Test Set).

Calculate MAE (Mean Absolute Error) and RMSE (Root Mean Square Error) for all three models.

Visualization: Create a single plot showing: Actual Price vs. ARIMA Prediction vs. LSTM Prediction.