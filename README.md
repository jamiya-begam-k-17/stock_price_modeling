# Stock Price Modeling with AR & MA Models

Time series analysis of Apple Inc. stock prices using AutoRegressive (AR) and Moving Average (MA) models.

## Dataset
- **Source**: Apple Inc. (AAPL) historical stock data
- **Features**: Open, High, Low, Close, Adj Close, Volume
- **Target**: Close price

## Methodology

1. **Stationarity Check**: ADF test (p-value: 0.3302 → non-stationary, differencing applied)
2. **Model Selection**: ACF/PACF plots to determine optimal lags
3. **Models Fitted**:
   - AR(3): Autoregressive model with 3 lags
   - MA(2): Moving Average model with 2 lags  
   - ARMA(3,2): Combined model

## Results

| Model | AIC | BIC | RMSE (last 50 points) |
|-------|-----|-----|----------------------|
| AR(3) | 5023.76 | 5048.54 | - |
| MA(2) | 5033.37 | 5053.20 | - |
| ARMA(3,2) | 5035.90 | 5070.62 | 2.3182 |

**Best Model**: AR(3) (lowest AIC/BIC)

## Key Findings
- Original series is non-stationary (ADF p-value > 0.05)
- ARMA residuals pass Ljung-Box test (p=0.53), indicating no significant autocorrelation
- 10-day forecast generated successfully

## Dependencies
```
pandas, matplotlib, seaborn, statsmodels, numpy, scikit-learn
```

## Usage
```python
python stock_price_modeling.py
```