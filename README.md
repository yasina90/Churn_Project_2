# Churn_Project_2

# 📊 Customer Churn Modeling

A machine learning project to analyze and predict customer churn. This project aims to identify the factors contributing to customer loss and build a predictive model to proactively retain valuable users.

---

## 🧠 Objective

- Understand what drives customer churn
- Build predictive models to identify high-risk customers
- Support business decisions for customer retention

---

## 📁 Dataset Overview

- **Total records**: 8,453 customers  
- **Target column**: `CHURN`  
  - `1` = Customer churned  
  - `0` = Customer stayed

- **Features include**:
  - Customer metadata: `PID`, `CRM_PID_Value_Segment`, `EffectiveSegment`, `Billing_ZIP`, `KA_name`
  - Subscriber counts: `Active_subscribers`, `Not_Active_subscribers`, `Suspended_subscribers`, `Total_SUBs`
  - Financial data: `AvgMobileRevenue`, `AvgFIXRevenue`, `TotalRevenue`, `ARPU`

---

## 🧹 Data Preprocessing

- Handled missing values:
  - Dropped rows with missing values in `CRM_PID_Value_Segment` and `Billing_ZIP`
- Encoded categorical features using:
  - `map()` for binary columns (e.g., Yes/No → 1/0)
  - One-hot encoding for multi-class categorical features
- Checked and corrected class imbalance where applicable
- Scaled numeric features if needed (optional)

---

## 📈 Exploratory Data Analysis (EDA)

- Distribution of churn vs non-churn
- Revenue and ARPU comparison
- Correlation heatmaps
- Segment-wise churn rates

---

## 🤖 Modeling

- Models tested:
  - Logistic Regression
  - Random Forest
  - XGBoost / LightGBM (optional)
- Evaluation Metrics:
  - Accuracy
  - Precision, Recall, F1-score
  - Confusion Matrix

---

## 🔍 Results (Current Best Model)

### 📉 Confusion Matrix:
``` 
  [[1004 577]
    [ 54 55]]
```

### 📊 Classification Report:
| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| 0 (Stayed) | 0.95 | 0.64 | 0.76 | 1581 |
| 1 (Churned) | 0.09 | 0.50 | 0.15 | 109 |

- **Accuracy**: 63%  
- **Macro Avg F1-score**: 0.45  
- **Observation**:
  - The model is heavily biased toward predicting "no churn" (class 0)
  - It has low precision on actual churners (class 1), though recall is moderate
  - **Imbalanced data** seems to be a key challenge

👉 Consider:
- Using **SMOTE** or other resampling techniques
- Trying **class weights** in your models
- Using ensemble methods for better minority class handling

---


# 📌  Requirements

Python ≥ 3.8

* pandas, numpy

* scikit-learn

* matplotlib, seaborn

* xgboost 
