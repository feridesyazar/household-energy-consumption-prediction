# ⚡ Household Energy Consumption Prediction

**Supervised Learning | Time Series Regression | Linear Regression**

This project predicts the **next hour's average household active power demand (kW)** using previous power measurements and calendar features.

## Project Goal

Can we predict the next hour's average household active power from recent and historical consumption patterns?

## Dataset

- **Name:** Individual Household Electric Power Consumption
- **Original source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)
- **Kaggle version:** [Electric Power Consumption Data Set](https://www.kaggle.com/datasets/uciml/electric-power-consumption-data-set)
- **Measurements:** 2,075,259 minute-level records from December 2006 to November 2010
- **Target:** Next hour's mean `Global_active_power`, measured in **kW** (average power, not energy in kWh)

The notebook loads the date, time, and active power columns, converts the readings into **hourly averages**, and excludes modeling rows with unavailable features or targets.

## Methods

- Data loading and cleaning with Pandas
- Hourly resampling and exploratory data analysis
- Feature engineering: current power, 24-hour and 168-hour lags, and calendar features
- Chronological **80% training / 20% testing** split
- Linear Regression
- Previous-hour persistence baseline
- Evaluation using **MAE, RMSE, and R²**
- Actual vs. Predicted visualization and residual analysis

## Results

| Model | MAE (kW) ↓ | RMSE (kW) ↓ | R² ↑ |
|---|---:|---:|---:|
| Previous-hour baseline | 0.399 | 0.605 | 0.353 |
| **Linear Regression** | **0.396** | **0.549** | **0.467** |

Linear Regression outperforms the baseline, particularly in RMSE. However, the R² of **0.467** shows that forecasting performance remains limited and could be improved.

## Conclusion

The project demonstrates a simple, reproducible approach to **one-step-ahead time series forecasting** with Linear Regression. Future work could explore nonlinear models, richer time-based features and better handling of high-demand periods.
