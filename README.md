# 🏠 California Housing – Linear Regression Models

## 📌 Project Overview
This project explores the **California Housing dataset** to predict the median house value.  
The focus is on applying linear regression techniques and observing their performance.  

---

## 🗂 Dataset
- Source: [California Housing (Kaggle)](https://www.kaggle.com/datasets/camnugent/california-housing-prices)  
- Features:  
  - `longitude`, `latitude`, `housing_median_age`, `total_rooms`,  
    `total_bedrooms`, `population`, `households`, `median_income`,  
    `ocean_proximity` (one-hot encoded).  
- Target:  
  - `median_house_value` (capped at 500,001).  

---

## ⚙️ Workflow
1. **Data Cleaning**
   - Filled missing values in `total_bedrooms` with median  
   - One-hot encoded `ocean_proximity`  
   - Converted categorical dummies to integer (0/1)  

2. **EDA**
   - Correlation heatmap showed **median_income** as the strongest predictor (r ≈ 0.69)  
   - Strong multicollinearity among `total_rooms`, `total_bedrooms`, `population`, `households`  

3. **Modeling**
   - Linear Regression (baseline)  
   - Ridge Regression (regularization)  
   - Lasso Regression (feature selection attempt)  
   - Elastic Net (Ridge + Lasso balance)  

---

## 📊 Results
| Model            | R²   | Adj R² | Notes |
|------------------|------|--------|-------|
| Linear           | 0.641 | 0.640 | Baseline |
| RidgeCV          | 0.641 | 0.640 | Stabilized coefficients |
| LassoCV          | 0.641 | 0.640 | Did not drop features, shrank coefficients |
| ElasticNetCV     | 0.641 | 0.640 | Balanced Ridge + Lasso |

---

## 📌 Key Takeaways
- Linear models can explain only ~64% of variance in house prices.  
- **Median income** is the strongest predictor.  
- Dataset is complex and capped → non-linear models (Random Forest, XGBoost) would likely perform better.  

---

✨ This project is part of my journey into Machine Learning and Regression modeling.
