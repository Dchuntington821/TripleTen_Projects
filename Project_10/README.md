<b> Project Description </b>

The company, Sweet Lift Taxi needs a predictive model that can predict that number of taxi orders for the next hour. Build a Time Series Regression model that can accurately predict the number of taxi rides over time, RMSE must be lower than 48. One dataset was provided.

<b> Data Loading and Cleaning </b>
1. Load in the dataset ensuring that date is loaded as indexed and is parsed correctly.
2. Check for any missing values - None were present

<b> Resampling </b>

I resampled the data by the sum of orders for each hour and then looked at the descriptive statistics. 

<b> EDA </b>

1. Plotted the time series to get a macro view of the data.
2. Plotted the data again using statsmodels.seasonal_decompose() to view the trends, seasonality and residuals.
3. Took a small slice of the data in-order to examine the trend and seasonality over the period of one day, this allowed me to 'blow up' the image and better view the trends and seasonality.
4. Completed an adfuller test to check for stationarity - The p-value was 0.05 indicating that the data is most likely stationary.

<b> Pre-Processing and Feature Engineering </b>

1. First, I created 10 features from the time series including day, hour, month, year, rolling mean and four additional lags.
   * I then plotted the data again, highlighting the rolling mean to ensure accuracy.
2. Split the data using Sklearn.train_test_split()
3. I then separated the data three different ways so that it was compatible with ARMA models, pmdarima models and traditional machine learning models.

<b> Time Series Regression Models </b>
Plotted ACF and PACF charts to determine an approximate number of lags for both MA and AR parameters

1. Auto Regression - statsmodels.auto_reg
2. Auto Regression - statsmodels.ARIMA
3. ARMA - statsmodels.ARIMA
4. PMDARIMA - pmdarima.auto_arima
5. Linear Regression - Sklearn
6. Decision Tree Regressor - Sklearn
7. Random Forest Regressor - Sklearn
8. LGBMRegressor, boosting_type = 'gbdt' - LightGBM
9. LGBMRegressor, boosting_trype = 'rf' - LightGBM

<b> Final Model Results </b>

All of the time series regression models failed to achieve and RMSE < 48. 

The best performing model was the LGBMRegressor with gbdt boosting type. It returned an RMSE of 44

