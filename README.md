# 📈 Euro–USD Exchange Rate Prediction

A Machine Learning Project for Forecasting EUR/USD Forex Prices

## Project Overview

This project aims to predict the Euro to US Dollar (EUR/USD) exchange rate using historical daily data. We build a complete ML pipeline, perform exploratory data analysis, handle missing values & outliers, engineer features, train multiple models, and evaluate their performance.

The project includes:

- Data Exploration
- Feature Engineering
- Outlier Handling
- Model Training & Evaluation
  - Linear Regression
  - Random Forest Regressor
  - XGBoost Regressor
- Model Comparison
- Prediction Visualization

The final goal is to select the best-performing model and prepare the project for deployment (API or Dashboard).

---

## Dataset Description

The dataset contains daily EUR/USD exchange rate values:

| Column | Description |
|--------|-------------|
| **Date** | Daily timestamp |
| **Price** | Closing EUR/USD price |
| **Open** | Opening price |
| **High** | Highest price of the day |
| **Low** | Lowest price of the day |
| **Vol.** | Volume (sometimes empty) |
| **Change %** | Daily percentage change |

You must clean missing values and convert `Change %` from string to numeric.

---

## Exploratory Data Analysis (EDA)

The notebook performs the following analyses:

### ✔ Missing Values Check
Identify and handle missing values.

### ✔ Outlier Detection
Use IQR method to detect and replace outliers in `Change %`.

### ✔ Trend Visualization
Plot:
- Daily closing price
- Rolling averages
- Change % (cleaned & smoothed)

### ✔ Feature Correlation
Display heatmap to find relationships between price, volatility, and engineered features.

---

## Feature Engineering

To improve model prediction capability, the following features are created:

- **Price_lag1** → previous day's price
- **Price_rolling7** → 7-day moving average
- **Volatility** → `High - Low`
- **Cleaned Change %**

These features allow machine-learning models to understand past behavior and patterns.

---

## Machine Learning Models

We train and evaluate three ML models:

### 1️⃣ Linear Regression
Baseline model to compare performance.

### 2️⃣ Random Forest Regressor
Non-linear, ensemble-based method. 👉 **Best performing model in this project.**

### 3️⃣ XGBoost Regressor
Boosting-based algorithm, strong for tabular data.

---

## Model Performance

| Model | RMSE (↓) | R² (↑) |
|-------|----------|--------|
| **Random Forest** | 0.003268 | 0.999704 |
| **XGBoost** | 0.007037 | 0.998629 |
| **Linear Regression** | 0.007880 | 0.998282 |

### Best Model: Random Forest Regressor

It achieved the lowest RMSE and highest R², making it the most reliable model for EUR/USD forecasting.
