# Time Series Forecasting with SARIMAX: Hospitality Employees Dataset

This project applies **Time Series Analysis** using the **SARIMAX** model to forecast the number of employees in the hospitality sector over time. The analysis involves visualizing the data, decomposing the time series, identifying seasonal patterns, and fitting a SARIMAX model for accurate forecasting.

## Project Objective

To model and forecast the monthly number of hospitality employees using a seasonal time series model (SARIMAX), and understand trends, seasonality, and residual behavior in the dataset.

---

## Dataset Overview

The dataset used in this project contains monthly data on the number of hospitality employees in the U.S. from January 1990 to december 2018.

- *Frequency*: Monthly
- *Type*: Univariate time series
- *Target Variable*: Number of employees in the hospitality sector

---

## Libraries Used

- `pandas`
- `matplotlib`
- `statsmodels`
- `numpy`

---

## Key Steps in the Project

1. *Exploratory Data Analysis*:
   - Time series plot to visualize trends.
   - Decomposition into trend, seasonal, and residual components.

2. *Stationarity Testing*:
   - ADF (Augmented Dickey-Fuller) Test to assess stationarity.
   - The Null and Alternate Hypothesis for the ADF test is,
     - Null: The given Data is non-stationary.
     - Alternate: The given Data is stationary.
   - We perform the test for a 95% confidence interval, that is, level of significance(alpha) is 0.05.
   - we then compare the p-value of the ADF test to the level of significance, wherein, if p-value < alpha, we reject the null hypothesis, otherwise not.

3. *Model Selection*:
   - Grid search for optimal SARIMAX parameters `(p,d,q)(P,D,Q,s)` using AIC as the selection criterion.
   - Here,
       - **p**: Order of non-seasonal autoregressive (AR) terms
       - **d**: Number of non-seasonal differences needed for stationarity
       - **q**: Order of non-seasonal moving average (MA) terms
       - **P**: Order of seasonal autoregressive terms
       - **D**: Number of seasonal differences
       - **Q**: Order of seasonal moving average terms
       - **s**: Length of the seasonal cycle (e.g., 12 for monthly data)

4. *Model Training*:
   - Fit the SARIMAX model on the training data.

5. *Predicting*:
   - Predict future values and compare against actual data.
   - Plot Predicted vs. observed values.

6. *Model Diagnostics*:
   - Analyze residuals to validate model.

7. *Training and Forecasting*:
   - Training the model again on the entire dataset
   - Forecasting values in the unknown future.
   - Plotting the given and the forecasted values.
