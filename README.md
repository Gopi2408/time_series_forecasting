# time_series_forecasting
German Electricity Demand Forecasting
Project Overview

This project studies whether the SARIMA model with the lowest training AIC also provides the best two-year electricity-demand forecast.

German hourly electricity-demand data are aggregated into weekly values and divided chronologically into training and testing periods.

Main Tasks
Clean and aggregate German electricity-demand data
Plot the original and differenced series
Perform ADF and KPSS stationarity tests
Examine autocorrelation
Create Mean, Naive, Seasonal Naive and Drift benchmarks
Test 147 SARIMA parameter combinations
Rank SARIMA candidates using AIC
Compare AIC ranking with test RMSE and MAE
Inspect residuals using ACF, histograms and Ljung–Box tests
Build a temperature-based SARIMAX model
Compare statistical and machine-learning forecasts
Dataset
Hourly German electricity demand
Period: January 2015 to October 2020
Weekly observations: 301
Training observations: 197 weeks
Testing observations: 104 weeks
Main Libraries
pandas
numpy
matplotlib
statsmodels
scikit-learn
requests
joblib
Installation
pip install pandas numpy matplotlib statsmodels scikit-learn requests joblib
How to Run
Open the notebook in Jupyter Notebook or Google Colab.
Install the required libraries.
Keep internet access enabled for data retrieval.
Run all cells in order.
Allow the SARIMA grid search to complete.
Review the generated plots, residual diagnostics and metric tables.
Main Result

The lowest-AIC model was:

SARIMA(2,0,2)(1,0,1,52)

Its test RMSE was:

3462.86 MW

The third-ranked AIC model was:

SARIMA(1,0,2)(1,0,1,52)

It achieved the best test RMSE:

2904.45 MW

This shows that the model with the lowest training AIC did not produce the strongest out-of-sample forecast.

Important Note

The current Random Forest result should not be used in the final comparison because its recursive history includes test-period observations. The model must be rerun using training history only.

Conclusion

AIC is useful for selecting a shortlist of statistical models, but final model selection should also consider residual diagnostics and genuine out-of-sample forecasting performance.
