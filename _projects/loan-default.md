---
title: Loan Default Prediction
layout: default
---

# Loan Default Prediction using Machine Learning

[View Code on GitHub](https://github.com/freakingdark/Loan_Payback_Prediction)

---

## Project Overview

This project builds a machine learning model to predict whether a borrower will repay a loan.  
The dataset contains **593,994 borrower records** with financial and demographic attributes.

The project follows a full **end-to-end data science workflow** including:

- Exploratory Data Analysis
- Feature Engineering
- Model Training
- Model Evaluation

The final model achieved **ROC-AUC ≈ 0.92** using **LightGBM with stratified 5-fold cross-validation**.

---

## Dataset

| Feature | Description |
|------|------|
| annual_income | Borrower's annual income |
| debt_to_income_ratio | Debt relative to income |
| credit_score | Creditworthiness score |
| loan_amount | Amount borrowed |
| interest_rate | Loan interest rate |
| gender | Borrower gender |
| marital_status | Marital status |
| education_level | Education level |
| employment_status | Employment category |
| loan_purpose | Loan usage |
| grade_subgrade | Lending risk grade |
| loan_paid_back | Target variable |

Dataset size:

- **Training:** 593,994 records  
- **Test:** 254,569 records

---

## Exploratory Data Analysis

Initial analysis examined:

- target class distribution
- financial feature distributions
- outliers
- categorical relationships

### Target Distribution

![Target Distribution](/assets/img/loan_target_distribution.png)

The dataset is **class imbalanced**, with roughly **80% of loans repaid**.

---

## Risk Analysis

Risk curves reveal important financial relationships.

Key observations:

- Higher **credit scores** correspond to lower default risk
- Higher **debt-to-income ratios** increase default probability
- Higher **interest rates** indicate higher borrower risk

---

## Feature Engineering

Several financially meaningful features were created:

**loan_to_income_ratio**

Loan size relative to income.

**interest_income_ratio**

Measures the relative interest burden.

**credit_score_bucket**

Credit score grouped into risk tiers.

**dti_risk**

Categorization of debt-to-income levels.

These engineered variables improve predictive power and interpretability.

---

## Model Training

The model was trained using **LightGBM**, a gradient boosting framework optimized for tabular datasets.

Training configuration:

n_estimators = 1500
learning_rate = 0.01
max_depth = 6
num_leaves = 31
subsample = 0.8
colsample_bytree = 0.8


Validation strategy:

- **Stratified 5-Fold Cross Validation**
- Early stopping
- Gradient boosted decision trees

---

## Model Performance

| Fold | ROC-AUC |
|-----|------|
| Fold 1 | 0.921 |
| Fold 2 | 0.920 |
| Fold 3 | 0.919 |
| Fold 4 | 0.920 |
| Fold 5 | 0.919 |

**Final ROC-AUC: 0.920**

This indicates strong ability to distinguish between likely repayment and default.

---

## Model Evaluation

Several diagnostic plots were generated:

### ROC Curve

![ROC Curve](/assets/img/loan_roc_curve.png)

### Confusion Matrix

![Confusion Matrix](/assets/img/loan_confusion_matrix.png)

### Feature Importance

![Feature Importance](/assets/img/loan_feature_importance.png)

---

## Key Insights

- **Credit score** is the strongest repayment predictor
- **Debt-to-income ratio** strongly influences default risk
- **Employment status** significantly affects repayment probability
- Feature engineering improves model interpretability and accuracy

---

## Technologies Used

Python  
Pandas  
NumPy  
Scikit-learn  
LightGBM  
Matplotlib  
Seaborn  
Jupyter Notebook

---

## Future Improvements

Possible extensions:

- Hyperparameter optimization using **Optuna**
- Model ensembling (LightGBM + CatBoost + XGBoost)
- Feature interaction engineering
- Probability calibration

---

## Author

Deepali Pandey  
Data Analyst | Machine Learning | Python


