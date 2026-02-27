# Demand Forecasting & Inventory Optimization

## Project Overview
This project implements an **end-to-end demand forecasting and inventory optimization pipeline** using large-scale retail time-series data.  
The objective is to **forecast daily demand at store–item level** and convert predictions into **actionable inventory decisions**.

---

## Problem Statement
Retailers struggle with:
- **Stock-outs**, leading to lost sales
- **Over-stocking**, increasing holding costs

This project addresses both by combining **time-series machine learning** with **inventory optimization techniques**.

---

## Dataset Description
- **Granularity:** Daily sales  
- **Time span:** 2019 – 2023  
- **Scale:** 4.5M+ records  
- **Entities:** Multiple stores and items  

**Key features**
- `date`, `store_id`, `item_id`
- `sales`, `price`, `promo`
- `weekday`, `month`

> The dataset is synthetic but designed to closely mimic real-world retail demand patterns such as trend, seasonality, pricing effects, and promotions.

---

## Methodology

### 1. Data Preprocessing
- Sorted time-series data by store and item
- Recomputed calendar features from date to avoid leakage
- Validated data quality

### 2️. Exploratory Data Analysis
- Sales trends and seasonality
- Promotion impact on demand
- Volatility across SKUs

### 3️. Feature Engineering
- Lag features (1, 7, 14, 28 days)
- Rolling averages (7, 14, 28 days)
- Price and promotion signals

---

## Models Used

### Baseline Models
- **Naive Forecast** (previous day demand)
- **Moving Average (7-day)**

### Machine Learning Models
- **LightGBM (global model)**
- **XGBoost** (optional comparison)

All models are evaluated using **time-based train–test splits**.

---

## Evaluation Metrics
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

Baseline models establish a reference point, while ML models demonstrate measurable improvement.

---

## Inventory Optimization
Forecasted demand is converted into inventory decisions using:
- Lead time assumptions
- Safety stock calculation
- Reorder Point (ROP)
- Stock-out risk simulation at SKU level

---

## Key Insights
- ML models outperform statistical baselines
- Lagged demand and rolling features are dominant predictors
- Conservative reorder policies significantly reduce stock-out risk
- Demonstrates a complete **forecast → decision pipeline**

---

## Business Impact
The solution supports:
- Better demand planning
- Reduced stock-outs and excess inventory
- Data-driven replenishment decisions

---

## Future Enhancements
- Probabilistic forecasting
- Dynamic service levels
- Real-time retraining
- Dashboard integration

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- LightGBM, XGBoost
- Matplotlib, Seaborn
- Google Colab

---

## Author
**Laiba Ali Naqvi**  
B.Tech (AI & ML)

---

