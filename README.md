# Sales Analysis & Prediction

Analyzing retail sales data to uncover business insights and predicting future sales using a Random Forest Regressor, based on the Superstore Sales dataset.

---

## Problem Statement
Retail businesses need to understand what drives sales and identify underperforming products before they become a financial liability. This project analyzes sales patterns across regions, categories, and time, then builds a model to predict future sales.

---

## Dataset
- **Source:** [Superstore Sales Dataset — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **Size:** 9,994 orders, 21 columns
- **Target:** Sales

---

## Workflow
1. Data loading and exploration
2. Data cleaning — dropped non-informative columns (Row ID, Customer ID, Product Name, Country)
3. Feature engineering — extracted Order Month, Order Year, and Shipping Days from date columns
4. Exploratory Data Analysis — profit by region, category, subcategory, discount impact, seasonal trends
5. Preprocessing — One-Hot Encoding, train/test split, StandardScaler
6. Modeling — Random Forest Regressor
7. Evaluation — MAE, MSE, R2, feature importance

---

## Results

| Metric | Score |
|--------|-------|
| MAE | $215.99 |
| MSE | $467,139.96 |
| R2 | 0.21 |

---

## Key Findings
- **West region** is the most profitable, **Central** generates high sales but low profit
- **Tables, Bookcases, and Supplies** are loss-making despite significant sales volume
- **High discounts kill profit** — subcategories averaging above 30% discount tend to lose money
- Sales show a clear **seasonal pattern** — Q4 peaks every year with consistent year-over-year growth
- **Quantity ordered** is the strongest predictor of sales value

---

## Data Leakage Detection
Profit was initially included as a feature and dominated the model at 0.85 importance — because Profit is calculated directly from Sales, making it a leaking feature. It was removed and the model was retrained on honest features only.

---

## Business Insights
- Reduce or eliminate discounts on Tables and Bookcases — they sell well but lose money
- Focus marketing efforts on Q4 when customers are most likely to buy
- Central region needs a pricing or cost strategy review despite strong sales volume

---

## Libraries Used
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
