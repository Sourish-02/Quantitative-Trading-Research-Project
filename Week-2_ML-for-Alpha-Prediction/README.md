# Week 2 Report — Machine Learning for Alpha Prediction

## Objective
The objective of this week's project was to develop machine learning models capable of predicting future returns through feature engineering, statistical analysis, and supervised learning.

---
## Dataset
The dataset consisted of historical market features together with a continuous target representing future returns.
Separate training and testing datasets were provided for model development and competition submission.

---
## Exploratory Data Analysis

The dataset was analysed through:
- Missing value analysis
- Target distribution
- Feature-target correlations
- Feature-feature correlations

The analysis revealed strong correlations among several raw price features and motivated the development of engineered features.

---
## Feature Engineering

Several new predictive variables were constructed, including:

- Return-based features
- Moving-average ratios
- Volatility features
- Candlestick features
- Calendar-based features
- Interaction features

Feature importance analysis was later used to evaluate their usefulness.

---
## Modelling

The following models were investigated:

- Ridge Regression
- Scaled Ridge Regression
- XGBoost Regression
- Hyperparameter Tuned XGBoost
- Robust Huber Regression
- Ensemble Models

TimeSeriesSplit cross-validation was used throughout to avoid look-ahead bias.

---
## Training Configuration

|Parameter|Value|
|---|---|
|Cross Validation|TimeSeriesSplit|
|Baseline Model|Ridge Regression|
|Main Nonlinear Model|XGBoost|
|Hyperparameter Search|RandomizedSearchCV|
|Final Models|Huber + XGBoost Ensemble|

---

## Results
Although extensive feature engineering and hyperparameter optimisation were performed, most models achieved negative out-of-sample R² scores, indicating that the prediction task was inherently difficult.

Important observations included:

- Original engineered features outperformed many newly created features.
- Excessive hyperparameter regularisation caused XGBoost to converge toward mean prediction.
- Robust regression slightly improved stability under outliers.
- Ensemble models produced more stable predictions than individual models.

These findings highlighted the challenges of predicting short-term financial returns and reinforced the importance of careful feature design.

---

## Key Learnings

- Performing exploratory analysis on financial datasets.
- Applying time-series aware cross-validation.
- Comparing linear and nonlinear regression models.
- Hyperparameter optimisation using RandomizedSearchCV.
- Building ensemble forecasting models.
- Understanding the limitations of machine learning in noisy financial markets.
