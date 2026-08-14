# Electricity-Consumption-Forecasting-Deep-Learning-Project-

<p align="center">
  <img src="https://github.com/user-attachments/assets/0f2ad37e-fc6a-49f5-8004-9c923cbe41e5" width="700">
</p>

## Team for the project

| Field | Details |
|------|---------|
| Name | Pradnya Tendolkar |

## Brief Summary of the Project

This project focuses on time series forecasting for hourly electricity consumption using the PJM dataset. The goal is to predict future PJMW_MW values from historical Datetime and load data so that power operators can better plan generation, reserves and pricing. Since the PJM load series shows strong autocorrelation along with clear daily and weekly seasonality, longer term trends, holiday effects and occasional shocks, sequence aware deep learning models are well suited for this task. Building on insights from recent research, I will implement and test multiple architectures from scratch such as LSTM, StackedLSTM, BiLSTM and other promising models and evaluate them using standard forecasting metrics like MAE, RMSE and MAPE. The final objective is to compare these approaches fairly and determine which deep learning model performs best for PJM electricity demand forecasting.

## About the dataset

I would be using the PJM Hourly Energy Consumption dataset from Kaggle which is originally from PJM Interconnection. Specifically, I will be working with the PJMW_hourly.csv file. It is a clean two columned time series dataset with an hourly Datetime index and load in megawatts(MW). The sample spans approximately from 2001 to 2018 with typical demand ranging from 14.5k to 62k MW. 

Dataset Link:
https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption?select=PJMW_hourly.csv

## Methodology

- Performed exploratory data analysis to understand trends, seasonality and distribution (time series plots, histograms).
- Engineered calendar-based features such as weekend indicator and US holidays to capture behavioral patterns.
- Created lag features (t-1 to t-5) to model temporal dependencies in electricity usage.
- Applied time-based splitting into train, validation and test sets to preserve sequence integrity.
- Standardized features and prepared sequence data (24-hour windows) for deep learning models.
- Implemented multiple models:
  - Naive baselines (last value, seasonal 24-hour)
  - Random Forest (traditional ML baseline)
  - LSTM, Stacked LSTM and BiLSTM (deep learning models)
- Used PyTorch for training with early stopping and optimized using Adam optimizer.

## Results

- Naive models provided baseline performance with higher error.
- Random Forest significantly improved accuracy (R² ≈ 98%).
- Deep learning models outperformed traditional methods:
  - LSTM: R² ≈ 99.46%
  - BiLSTM: R² ≈ 99.50%
  - Stacked LSTM: Best performance with R² ≈ 99.54% 
- Achieved low MAE, RMSE and MAPE, indicating strong predictive performance.
- Final comparison confirms Stacked LSTM as the best model.

## Reflection and Analysis

- Time series patterns such as daily cycles and seasonality were effectively captured using lag features and sequence modeling.
- Deep learning models performed better due to their ability to learn temporal dependencies compared to traditional ML.
- Residual analysis showed errors are generally low but slightly higher during peak usage hours.
- Model generalizes well across unseen test data, indicating minimal overfitting.
- Limitation: performance depends on historical patterns. Sudden anomalies or external factors (weather, outages) are not explicitly modeled.
- Overall, the pipeline demonstrates a strong, scalable approach for real-world electricity demand forecasting.
