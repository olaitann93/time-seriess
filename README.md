# Apple Stock Price Modelling and Forecasting

## Project Overview
This project analyzes historical stock data for Apple Inc. (AAPL) to identify trends and forecast future price movements. The goal is to model Apple stock price and predict price movements for the next one hundred (100) days.

## Data Source
* **Source:** Five (5) years historical data of Apple stock price was downloaded from Yahoo Finance  
* **Time Period:** Nov 02, 2020 - Oct 31, 2025  
* **Frequency:** Daily Adjusted Closing Prices  

## Tools Used
* **Language:** Python  
* **Libraries:** 'pandas', 'numpy', 'matplotlib', 'datetime', 'statsmodels', 'yfinance'

## Methodology
#### **Model Identification**
The chart of the Apple stock price showed a strong upward trend and clear autocorrelation in both the ACF and PACF plots.  
The return series, however, appeared stationary. Based on this behavior, an ARIMA(0,1,0) model was selected.


#### **Model Estimation**
The ARIMA(0,1,0) model was fitted using maximum likelihood estimation. The key parameter estimated was sigma² = 9.461, representing the variance of the residuals. The p-value < 0.001 indicates that the model is statistically significant.


#### **Model Diagnostics**
A series of diagnostic checks were conducted to evaluate whether the model fully captures the structure in the data.

##### 1.  **Residual Plot & ACF Plot**
- All residual ACF lags lie within confidence bounds 
- No visible autocorrelation pattern. However, residuals exhibit changing variance across time (heteroskedasticity). This suggests the presence of volatility clustering. 

##### 2.  **Ljung–Box Test**
- With all p-value > 0.05, residuals are truly independent, meaning the model adequately captures temporal dependence.

##### 3.  **QQ Plot**
- Residuals deviate from normality with pronounced fat tails on both ends.
 
--- 

## Forecast Result
There is 80% chance that Apple stock price will be between $230 and $310, and 95% chance that it will be between $210 and $340 for the next 100 days.

---

### **Conclusion**
The ARIMA(0,1,0) model successfully captures the mean behavior of the Apple stock return series but does not capture its changing volatility.  
Future work would consider volatility-sensitive models like GARCH or ARIMA-GARCH.


