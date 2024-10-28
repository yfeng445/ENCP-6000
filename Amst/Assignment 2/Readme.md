# Stock Price Prediction and Technical Analysis Project

## Overview
Please start to prepare for your second presentation next week. For this project, you will predict stock prices using a combination of statistical models and technical analysis. This presentation will be your debut to the entire class:

First, for each stock you are working on,  please apply the GARCH model to forecast stock return (daily log return) and the Kalman Filter to predict daily stock prices. Visualize the predictive path versus the actual stock return/price history and the report the RMSE. 

Second, enhance your understanding of the training data using basic technical analysis indicators. Use moving averages (SMA/EMA) to identify trends, Relative Strength Index (RSI) to detect overbought or oversold conditions, and On-Balance Volume (OBV) to analyze buying or selling pressure. Additionally, analyze candlestick chart patterns such as Doji, Hammer, Hanging Man, and Bullish/Bearish Engulfing patterns to interpret potential market reversals.

Third, you may combine the insights from GARCH/Kalman Filter models and technical analysis indicators to make informed interpretation of your prediction results and explore basic stock market analysis.

## Breakdown

#### 1. Intro & Summary & Statistical Models for Stock Prediction (@xiaobinwang0, @Zzckin)
For each stock in the dataset, apply two statistical models to predict stock prices:

- **GARCH Model**:
  - Forecast stock return (daily log return) using the GARCH model.
- **Kalman Filter**:
  - Predict daily stock prices using the Kalman Filter.
- **Visualization**:
- Compare the **predicted path** against the **actual stock return/price history** using appropriate plots.
- **Performance Metrics**:
- Report the **Root Mean Square Error (RMSE)** to evaluate the accuracy of the models.

#### 2. Technical Analysis for Understanding Trends (@monica00zhang)
To enhance your understanding of the stock data, apply the following technical analysis indicators:

- **Trend Identification**:
  - Use **Simple Moving Averages (SMA)** and **Exponential Moving Averages (EMA)** to identify price trends.
- **Overbought/Oversold Detection**:
  - Use the **Relative Strength Index (RSI)** to identify overbought or oversold conditions. 
- **Buying/Selling Pressure**:
  - Analyze **On-Balance Volume (OBV)** to assess the pressure of buying or selling activity.
  
#### 3. Trade Pattern Identification (@MenggeLuo)
- **Candlestick Chart Patterns**:
  - Interpret market conditions using common candlestick patterns such as:
    - **Doji**
    - **Hammer**
    - **Hanging Man**
    - **Bullish/Bearish Engulfing**

#### 4. Integration of Insights (@yfeng445, @liyueyueli)
Combine the insights from both statistical models (GARCH and Kalman Filter) and technical analysis to:

- Determine the stationary using ADF and KPSS test if the stock price is stationary (or random walk), build a pipeline as a step of preprocessing.
- Calculate the degree of freedom and kurtosis, determine which garch model to use. (garch/garch-t/garch-mixture)
- Calculate the distribution: Gaussian => Kalman filter, non-Gaussian => Particle Filter
- Build Mean Reversion Strategy model based on Garch and Kalman Filter, garch model works best with stationary time series, MA works good for non-stationary case.
- Test the model with Diebold-Mariano test. (predictive accuracy)
- Integrate Relative Strength Index with candlestick pattern.


