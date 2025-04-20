# 📈 Summary Report: Demand Planning & Forecasting  
**Author:** [github.com/scriptstorydude](https://github.com/scriptstorydude)  
**Project Title:** Store Item Demand Forecasting

---

## 🧩 Objective

The purpose of this project is to build a robust forecasting model to predict daily sales for 50 items across 10 stores using historical sales data. The task involves predicting sales for a 3-month period using 5 years of prior data, applying advanced feature engineering and machine learning techniques.

---

## 📊 Dataset Overview

- **Training Data:** 913,000 rows  
- **Test Data:** 45,000 rows  
- **Features:** `date`, `store`, `item`, `sales`  
- **Coverage:** January 1, 2013 – March 31, 2018  
- **Target:** Daily item-level sales per store

---

## 🧪 Project Workflow

### 1. Data Loading & Initial Exploration
- Combined `train.csv` and `test.csv` datasets.
- Verified shape, time span, and sales distributions.
- Explored unique item-store combinations (all stores carry all items).

### 2. Feature Engineering
- Extracted features from date: `month`, `day_of_week`, `day_of_month`, etc.
- Flags for weekends, month start/end.
- One-hot encoding for categorical variables.
- Applied log transformation to stabilize variance.

### 3. Lag & Trend Features
- **Lag Features:** Sales shifted by 91–728 days.
- **Rolling Means:** Triangular windows for smoothing trends (365–730 days).
- **EWMA Features:** Applied exponential smoothing with decay factors (`alpha`) from 0.5 to 0.99.

---

## 🤖 Modeling with LightGBM

- **Model Used:** LightGBM Regressor
- **Training Period:** Until end of 2016
- **Validation Period:** Jan–Mar 2017
- **Features:** 94 engineered columns
- **Custom Metric:** SMAPE (Symmetric Mean Absolute Percentage Error)

```python
SMAPE = (200 * |Forecast - Actual| / (|Forecast| + |Actual|))
```

- LightGBM trained with:
  - `num_leaves`: 10  
  - `learning_rate`: 0.02  
  - `max_depth`: 5  
  - `early_stopping_rounds`: 200  
  - `boosting_rounds`: 2000

---

## 📈 Model Performance

- **Best Validation SMAPE:** 13.62%  
- **Training SMAPE:** 13.13%

---

## 🔮 Forecasting Output

- Final model trained on entire dataset.
- Predictions generated for all item-store pairs.
- Forecasts visualized and compared to historical data for samples:
  - **Store 1 - Item 1**
  - **Store 1 - Item 17**

---

## 🚀 Key Takeaways

- Feature engineering significantly enhanced model accuracy.
- SMAPE proved reliable for evaluating sales prediction quality.
- Log transformation, lag windows, and EWMAs captured both trend and seasonality.
- LightGBM delivered scalable performance for large time series data.

---

Let us know if you'd like this turned into a downloadable PDF or added to your project README!
