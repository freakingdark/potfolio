---
title: Global Earthquake & Tsunami Risk Analysis
layout: default
---

# Global Earthquake & Tsunami Risk Analysis

[View Code on GitHub](https://github.com/freakingdark/Tsunami_Project)

---

## Project Overview

This project analyzes global earthquake data to identify characteristics of **tsunami-generating earthquakes** using statistical modeling and machine learning.

The study combines:

- Exploratory data analysis
- Geospatial visualization
- Extreme Value Theory (EVT)
- Logistic regression classification

The goal is to understand **risk patterns of high-magnitude earthquakes and tsunami probability**.

Dataset:  
Global Earthquake & Tsunami Risk Assessment Dataset (Kaggle)

---

## Analytical Components

The analysis consists of three major components:

1. Exploratory Data Analysis (EDA)
2. Extreme Value Modeling (Peak Over Threshold – GPD)
3. Tsunami Probability Classification

---

## Dataset Features

### Continuous Variables

- Magnitude
- Depth
- CDI (Community Decimal Intensity)
- MMI (Modified Mercalli Intensity)
- Gap
- Significance score
- Number of stations

### Spatial Variables

- Latitude
- Longitude

### Target Variable

Tsunami occurrence  
0 → No Tsunami
1 → Tsunami Event


---

## Exploratory Data Analysis

Initial analysis explores structural patterns in earthquake data.

Key investigations include:

- Tsunami vs non-tsunami class distribution
- Magnitude and depth distributions
- Intensity measure analysis
- Global earthquake spatial distribution
- Temporal trends

### Global Earthquake Map

![Global Map](/potfolio/assets/img/earthquake_map.png)

### Spatial Density (Hexbin)

![Spatial Density](/potfolio/assets/img/earthquake_hexbin.png)

### Depth Category Distribution

Depth categories:

- Shallow (0–70 km)
- Intermediate (70–300 km)
- Deep (300–700 km)

![Depth Distribution](/potfolio/assets/img/depth_distribution.png)

---

## Extreme Value Theory (EVT)

To model rare high-magnitude earthquakes, **Peak Over Threshold (POT)** modeling is applied.

Steps:

1. Threshold selected at the **95th percentile of earthquake magnitude**
2. Fit **Generalized Pareto Distribution (GPD)**
3. Estimate exceedance rate
4. Compute return periods

Key parameters:

- u → threshold
- ξ (xi) → shape parameter
- β (beta) → scale parameter
- λ → exceedance rate per year

Return period estimation:
T(x) = 1 / [ λ × (1 − G(x − u)) ]

This provides an estimate of how frequently extreme magnitude earthquakes occur.

Example:

Estimated return period for **magnitude ≥ 9 earthquakes**.

---

## Tsunami Classification Model

A probabilistic tsunami classifier is built using **logistic regression**.

Model:
LogisticRegression(class_weight="balanced")


Features used:

- Magnitude
- Latitude
- Longitude

Workflow:

1. Standardize features
2. Train logistic regression model
3. Compute predicted tsunami probabilities
4. Evaluate using ROC-AUC

The model estimates:
P(Tsunami | magnitude, latitude, longitude)


---

## Key Insights

Important findings from the analysis:

- Higher **magnitude earthquakes** significantly increase tsunami probability
- Tsunami-generating earthquakes tend to occur in **specific geographic regions**
- Extreme magnitude events follow heavy-tailed statistical behavior
- EVT provides useful estimates of **rare earthquake return periods**

---

## Technologies Used

Python  
Pandas  
NumPy  
SciPy  
Scikit-learn  
Matplotlib  
Seaborn  
Cartopy  

---

## Key Concepts Demonstrated

This project demonstrates several advanced analytical concepts:

- Extreme Value Theory
- Generalized Pareto Distribution
- Return period estimation
- Logistic regression classification
- ROC-AUC evaluation
- Geospatial data visualization
- Risk modeling

---

## Author

Deepali Pandey  
Data Analyst | Machine Learning | Python
