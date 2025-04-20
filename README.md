

# 🏪 Store Demand Planning and Forecasting


## 📌 Project Overview

This project focuses on building a predictive model to estimate item demand across different retail store locations using historical sales data. By applying machine learning techniques, the goal is to forecast future sales volumes for every store-item combination with improved accuracy.

---

## 📁 Directory Structure

├── LICENSE
├── README.md              <- You are here!
├── notebook             <- Jupyter notebooks for experimentation and analysis
│   └── demand_plan.py    <- Final forecasting notebook
├── output                <- Analysis reports and summaries
│   └── Report.pdf         <- Final project report
├── source                    <- Source code for data handling and model training
│   ├── data               <- Raw and processed datasets
│   └── model              <- Machine learning models


## 📊 Dataset Summary

The dataset includes transactional-level sales data from multiple stores and consists of:

- **`date`**: Sales date  
- **`store`**: Identifier for the store  
- **`item`**: Identifier for the product  
- **`sales`**: Units sold on a particular date at a specific store for a given item  

The test dataset mirrors the structure but omits the `sales` column, which the model will predict.

---

## 🧠 Why It Matters

Demand plannng and forecasting is essential in retail operations and supply chain optimization. Predicting future sales allows companies to better manage stock, reduce waste, and improve customer satisfaction by ensuring availability. Using historical data combined with time-series modeling techniques and machine learning, this project builds a solution that aims to solve these practical business challenges.

---

## 🎯 Project Goals

The aim is to create a data-driven predictive model that helps forecast demand at a granular level (per store and item) to support smarter inventory and promotional decisions.

---

## 🔍 Methodology

Our process follows these key stages:

1. **Data Ingestion & Exploration**: Understand trends, seasonality, and missing values.
2. **Feature Engineering**: Enhance predictive power by adding derived time-based features.
3. **Lag Features**: Incorporate historical sales performance to capture recurring patterns.
4. **Rolling Statistics**: Use moving averages to detect trends and smooth fluctuations.
5. **EWMA Features**: Apply exponentially weighted metrics for more recent data emphasis.
6. **Model Building**: Train models such as LightGBM tailored for tabular time-series data.
7. **Model Evaluation**: Use SMAPE and other metrics to validate forecast accuracy.
8. **Test Prediction**: Generate final demand predictions for the test set.
9. **Visualization**: Compare model forecasts against actuals visually for deeper insights.

---