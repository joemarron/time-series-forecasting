
# Time series forecasting - Exploring different techniques

This project was completed when I was learning time series forecasting techniques using Python. The coursework explored several forecasting techniques at various levels of sophistication from naive to ARIMA.

## Summary

#### The datasets included:
| DataFrame    | Description  |
| -------- | -------- |
| hwg_df | Harworth Group PLC (HWG) stock prices |
| eth_df | Ethereum prices |
| snp_df | S&P500 stock prices |
| daily_deaths | UK daily COVID deaths |
| UK_port_df | Traffic through UK ports |
| retail_df | US monthly retail sales |


#### Performance of Forecasting Techniques - Root Mean Squared Errors (RMSE)
Forecasting techniques that have been implemented and assessed are Naive, Seasonal Naive, Averaging, Difference Averaging, Exponential Decomposition, Lowess Decompostion, STL Decomposition, ARMA, ARIMA and SARIMAX. STL (Seasonal Lowess Trend) Decomposition performs best on most of the datasets with our manual implementations, however with pre-defined optimised algorithms, different results would likely be acheived.
|              | Naive    | S_Naive  | Avg      | Diff_Avg | AR(p)   | Exp_Decomp | Low_Decomp | STL_Decomp | ARMA   | ARIMA    | SARIMAX  | Best Alg   |
| ------------ | -------- | -------- | -------- | -------- | ------- | ---------- | ---------- | ---------- | ------ | -------- | -------- | ---------- |
| hwg_df       | 2.506    |          | 2.58     | 2.557    | 2.455   |            | 2.251      |            |        | 2.46     |          | Low_Decomp |
| eth_df       | 81.47    |          | 88.563   | 81.888   | 81.536  | 81.99      | 76.765     |            |        | 81.513   |          | Low_Decomp |
| snp_df       | 21.775   |          | 23.26    | 22.072   | 21.628  |            | 21.083     |            | 21.771 | 21.645   |          | Low_Decomp |
| daily_deaths | 24.85    |          | 27.784   | 23.603   | 24.672  |            | 20.524     |            |        | 24.835   |          | Low_Decomp |
| UK_port_df   | 61.638   | 74.931   | 56.702   | 62.113   | 56.09   |            | 48.037     |            |        | 60.026   |          | Low_Decomp |
| retail_df    | 33150.68 | 24153.52 | 26096.75 | 33637.87 | 28167.8 |            | 10185.24   | 5136.946   |        | 30915.95 | 13488.29 | STL_Decomp |


## Visualisation
### ARIMA Implementation on S&P500
As the below graph demonstrates, ARIMA forecasting is extremely powerful and can be optimised further than my implementation, hence its popularity in industry forecasting.

![ARIMA S&P500](https://github.com/joemarron/time-series-forecasting/blob/main/SP500%20ARIMA%20Prediction.png)

### Power of STL Decomposition on US Monthly Retail Sales
As the results show, STL can be extremely effective for a relatively simple technique, especially on seasonal data as the name suggests. The below demonstrates this, with a monte carlo simulation maintaining the seasonality for a respectable time horizon.

![STL_US_Sales](https://github.com/joemarron/time-series-forecasting/blob/main/US%20Retail%20Sales%20STL%20Decomp%20Monte%20Carlo%20Simulation%20(5y).png)

### Portfolio Simulations on HWG.L - AutoRegression v STL Decomposition
The below portfolio simulations show varying results when using predictions for AR(3) and STL Decomp. The parameters for this simple simulation are, given a starting portfolio value of £10,000 , if predicted value for day is a 4% above actual, then buy portfolio value worth of stock, if not, then sell whole position. This is obviously an unrealistic scenario but for demonstration provides useful results. As can be seen in the below graphs, a portfolio return of 22.4x was achieved for the STL Decomp simulation vs the AR(3) model. This shows the significance of choosing the most accurate model.

![AR_Sim](https://github.com/joemarron/time-series-forecasting/blob/main/Portfolio%20Simulation%20HWG%20-%20AutoRegression.png)

![STL_Sim](https://github.com/joemarron/time-series-forecasting/blob/main/Portfolio%20Simulation%20HWG%20-%20Lowess%20Decompostion.png)