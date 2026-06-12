# 🏠 California Property Price Prediction

Predicting median house values across California districts using regression models.

## 📌 Overview

This project builds predictive models to estimate housing prices in California districts using district-level features such as median income, number of rooms, geographic coordinates, and ocean proximity. Both Simple Linear Regression and Multiple Linear Regression are implemented and compared.

## 🎯 Problem Statement

Given a dataset of California housing districts, the goal is to predict the **median house value** and identify the key variables that influence it.

## 📂 Project Structure

```
california-property-price-prediction/
│
├── property_price_prediction.ipynb   # Main notebook
├── data/
│   └── Data_file.csv                 # Dataset
├── README.md
└── requirements.txt
```

## 🔧 Tech Stack

- Python 3.x
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook

## 📊 Workflow

1. **Exploratory Data Analysis (EDA)** — Distribution plots, correlation heatmaps, summary statistics
2. **Data Preprocessing** — Missing value imputation, encoding of categorical variables (e.g., `ocean_proximity`), feature engineering (`rooms_per_household`, `bedrooms_per_room`)
3. **Model Development**
   - Simple Linear Regression (using `median_income` as the single best predictor)
   - Multiple Linear Regression (all features)
4. **Model Evaluation** — MAE, MSE, RMSE, R² Score, 5-Fold Cross-Validation

## ✅ Results

### Simple Linear Regression

| Split | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Train | $55,338.66 | $72,645.93 | 0.44 |
| Test  | $55,902.92 | $73,136.99 | 0.44 |

### Multiple Linear Regression

| Split | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Train | $41,800.27 | $56,276.65 | 0.66 |
| Test  | $42,528.34 | $58,693.02 | 0.64 |

### Cross-Validation (MLR — 5-Fold)

| Mean R² | Std R² |
|---------|--------|
| 0.6612  | 0.0062 |

### Model Comparison Summary

| Model | Test RMSE | Test R² |
|---|---|---|
| Simple Linear Regression | $73,137 | 0.4417 |
| **Multiple Linear Regression** ✅ | **$58,693** | **0.6404** |

> **Selected Model: Multiple Linear Regression** — 45% improvement in R² and $14,444 reduction in RMSE over the simple model.

### Key Insights
- `median_income` is the single strongest predictor (R² ≈ 0.47 alone)
- Engineered features (`rooms_per_household`, `bedrooms_per_room`) improve R² further
- Coastal proximity (Bay Area, LA) significantly drives higher house values

## 🚀 Getting Started

```bash
git clone https://github.com/your-username/california-property-price-prediction.git
cd california-property-price-prediction
pip install -r requirements.txt
jupyter notebook property_price_prediction.ipynb
```

## 📋 Guidelines

- Data split: 80% training / 20% testing (15,094 train | 3,774 test samples)
- Hyperparameters tuned to improve performance
- All preprocessing, modeling, and evaluation steps documented in the notebook
