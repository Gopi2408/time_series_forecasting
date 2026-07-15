# time_series_forecasting
Forecasting for Reserve Adequacy — German Electricity Demand
Overview
This project forecasts German weekly electricity demand and compares models under a cost-sensitive framework where underforecasting (demand shortfall) is penalised more heavily than overforecasting. Models tested: benchmark forecasts (Mean, Naive, Seasonal Naive, Drift), SARIMA, SARIMAX with temperature and calendar covariates, Quantile Gradient Boosting (median and upper planning forecast), and an hourly LSTM. All models are evaluated on the last 2 years of data (104 weeks).
Data

German electricity load from Open Power System Data (hourly, 2015–2020) — downloaded automatically by the notebook
Berlin temperature from the Open-Meteo archive API — downloaded automatically by the notebook

No manual downloads needed.
Libraries to install
pip install pandas numpy matplotlib statsmodels scikit-learn tensorflow holidays requests
How to run

Open the notebook in Google Colab or Jupyter.
Run all cells from top to bottom (Runtime → Run all).
That's it — data downloads, models train, and all figures and tables are saved to the outputs folder automatically.

Internet connection is required on the first run to download the data. Full run takes a few minutes.
Results summary
The Seasonal Naive is the most accurate simple forecast but underforecasts most high-demand winter weeks. SARIMA and SARIMAX rarely underforecast, but only because they are biased high. The Quantile Gradient Boosting upper forecast gives the best balance — it cuts shortfalls by two thirds using an explicit reserve margin of about 1.9% of load, and is the recommended planning forecast. The LSTM is accurate hour-ahead but is a short-term tool, not a long-horizon planning forecast. See the report for full discussion, figures and tables.
