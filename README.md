# Electricity-Consumption-Forecasting-Deep-Learning-Project-

## Team for the project

| Field | Details |
|------|---------|
| Name | Pradnya Tendolkar |
| GWID | G45312425 |
| GitHub Username | pradtgit |

## Brief Summary of the Project

This project focuses on time series forecasting for hourly electricity consumption using the PJM dataset. The goal is to predict future PJMW_MW values from historical Datetime and load data so that power operators can better plan generation, reserves and pricing. Since the PJM load series shows strong autocorrelation along with clear daily and weekly seasonality, longer term trends, holiday effects and occasional shocks, sequence aware deep learning models are well suited for this task. Building on insights from recent research, I will implement and test multiple architectures from scratch such as LSTM, StackedLSTM, BiLSTM and other promising models and evaluate them using standard forecasting metrics like MAE, RMSE and MAPE. The final objective is to compare these approaches fairly and determine which deep learning model performs best for PJM electricity demand forecasting.

## About the dataset

I would be using the PJM Hourly Energy Consumption dataset from Kaggle which is originally from PJM Interconnection. Specifically, I will be working with the PJMW_hourly.csv file. It is a clean two columned time series dataset with an hourly Datetime index and load in megawatts(MW). The sample spans approximately from 2001 to 2018 with typical demand ranging from 14.5k to 62k MW. 

Dataset Link:
https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption?select=PJMW_hourly.csv
