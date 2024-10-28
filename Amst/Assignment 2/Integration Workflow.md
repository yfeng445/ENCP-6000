# Nvidia Stock Analysis Workflow

## 1. Enhanced Stationarity Check
- **Tests**: Conduct the following tests to determine if the stock price series is stationary:
  - Augmented Dickey-Fuller (ADF)
  - Kwiatkowski-Phillips-Schmidt-Shin (KPSS)
  - Phillips-Perron (PP)
- **Visual Checks**: Generate autocorrelation and partial autocorrelation plots for additional insights.
- **Transformations**: If non-stationary, consider transformations (e.g., differencing or log returns) to achieve stationarity.
- **Outcome**: Proceed with GARCH modeling if stationarity is confirmed.

## 2. Refined GARCH Model Selection
- **Initial Indicators**: Use kurtosis and degrees of freedom as initial filters, but add skewness and asymmetry checks.
- **Model Options**:
  - Standard GARCH: For symmetric volatility clustering.
  - GARCH-t or GARCH-mixture: For heavy-tailed data.
  - EGARCH or GJR-GARCH: For asymmetric volatility.
- **Model Evaluation**: Fit each model and use AIC/BIC criteria to select the best-performing GARCH model.

## 3. Distribution and Filtering Selection
- **Gaussianity Test**: Assess the residuals of the chosen GARCH model for Gaussianity using:
  - Skewness-kurtosis plots
  - Jarque-Bera test
  - Kolmogorov-Smirnov test
- **Filter Choice**:
  - Kalman Filter: If residuals are approximately Gaussian.
  - Particle Filter or Markov-Switching GARCH: If residuals are non-Gaussian or indicate multiple regimes.
- **Enhanced Filtering**: For Particle Filter use, set multiple particles to improve results.

## 4. Improved Mean Reversion Strategy
- **Mean Reversion Assessment**: Use the chosen GARCH model to determine if Nvidia’s returns exhibit mean-reverting behavior.
- **Model Choice Based on Trends**:
  - Stationary Series: Use a GARCH-based mean reversion model.
  - Non-stationary Series: Enhance with a moving average (MA) component or trend-following mechanism.
- **Stochastic Mean Reversion**: Consider a shifting mean with a Kalman Filter drift term if the trend is prominent.

## 5. Predictive Accuracy Testing with Diebold-Mariano (DM) and Harvey-Leybourne-Newbold (HLN) Tests
- **Diebold-Mariano Test**: Use DM to compare forecasting performance of non-nested models.
- **Harvey-Leybourne-Newbold Test**: Apply HLN for nested models (e.g., GARCH vs. GJR-GARCH).
- **Alternative Models**: If poor performance is noted, consider Bayesian GARCH or adding exogenous variables to capture market factors.

## 6. Relative Strength Index (RSI) and Candlestick Patterns Integration
- **Conditional RSI Application**: Apply RSI in periods of low volatility to avoid excessive noise in high volatility phases.
  - Optionally, apply an exponential moving average filter to smooth RSI signals.
- **Candlestick Patterns as Confirmatory Signals**: Use candlestick patterns to validate RSI indications rather than as primary triggers to reduce false positives.

## Summary of Adjustments
1. Expanded Stationarity Tests: Include PP and visual checks.
2. Model Selection Additions: Incorporate skewness and asymmetry checks.
3. Filter Selection Process: Use Gaussianity checks to guide filter choice and consider regime-switching models.
4. Adaptive Mean Reversion: Adjust based on Nvidia’s trend behavior.
5. Comprehensive Predictive Accuracy Testing: Use DM and HLN tests.
6. RSI Integration Strategy: Apply conditionally with filters for smoother signals.
