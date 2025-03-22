# Project Overview

## Time Series Forecasting for Household Devices
- **Description**: A machine learning project predicting household appliance energy consumption (Wh) over a month using time series data. Employs baseline, traditional, ML, deep learning, and transformer models, with preprocessing inspired by "Data-driven prediction models of energy use of appliances in a low-energy house."
- **Purpose**: Enhances energy management by forecasting load demand for optimization, demand-side response, and renewable integration.
- **Team**: Themistoklis Proko (03301), Georgios Kapakos (03165), Eleni Athanailidi (03453).
- **Course**: ECE461 - Machine Learning, University of Thessaly, Fall 2024-2025.
- **Instructor**: Ilias Houstis.
- **Submission**: January 20, 2025.

## Preprocessing
- **Dataset**: `Energydata_complete.csv` (19,440 samples, 10-min intervals, 4.5 months) with appliance energy, lights, weather, and house temp/humidity features.
- **Steps**:
  - **Feature Elimination**: Dropped `lights`, `rv1`, `rv2`, `visibility`.
  - **ACF Plot**: Added lags (1h, 2h, 3h, 6h, 12h, 1d, 2d, 3d) and rolling means (2h, 5h, 8h, 1d, 2d).
  - **Feature Engineering**: Lag features and rolling windows for temporal patterns.
  - **Missing Values**: Filled with column means.
  - **Outliers**: IQR method (threshold=1) for removal.
  - **Scaling**: Min-Max scaler selected.

## Forecasting Models
- **Baseline**: Naive (R²=-2.15), Moving Average (R²=-0.02), Seasonal Naive (R²=-0.73).
- **Traditional**: ARIMA/SARIMA tested, poor performance, excluded.
- **Machine Learning**: 
  - Decision Trees (R²=0.66), Random Forest (R²=0.76), XGBoost (R²=0.78).
- **Deep Learning**: 
  - LSTM (R²=0.997), GRU (R²=0.996), TCN (R²=0.95) - kept outliers for robustness.
- **Transformers**: Adapted for time series (R²=0.95), excels in long-range dependencies.

## Evaluation
- **Metrics**: RMSE, MAPE, R², MAE; R² prioritized.
- **Results**: LSTM best (R²=0.997), deep learning outperforms ML (XGBoost R²=0.78) and baseline.
- **Runtime**: Naive fastest (0.00006s), Random Forest slowest (200s), deep learning moderate (55-122s on T4 GPU).

## File Description
1. Machine-Learning-Final: A Report describing the project
2. ML-final-Project: A ppt presentation of the project
3. Team-26-final-project: The jupyter notebook containing the code for the project
4. energy-data-complete: The .csv file used for the project.


