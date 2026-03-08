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

