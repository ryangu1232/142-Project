# Predicting NBA Performance from Draft Combine Metrics

> **⚠️ Note: This repository is actively under development. Changes are still ongoing.**

A predictive modeling study analyzing how NBA Draft Combine measurements translate into on-court performance outcomes, with a focus on **points and rebounds prediction** using traditional statistical and machine learning models.

**Author:** Ryan Gu, Vatsal Garg, Tanishq Shinde, Akarsh Tripathi, Ziheng Zhang
**Course:** IEOR 142 – Fall 2025  
**Report:** TODO

---

## Project Overview

This project investigates the extent to which **pre-draft physical measurements and athletic testing data** can explain and predict **NBA player performance**, specifically:

- **Points per game (PTS)**
- **Rebounds per game (REB)**

Using NBA Draft Combine data merged with historical NBA player statistics, we compare:

1. **Classical Regression Models**
2. **Tree-Based Machine Learning Models** (Classification and Regression Trees, Random Forests)

The goal is to evaluate **predictive accuracy, feature importance, and model interpretability**, while addressing real-world data challenges such as missing values, multicollinearity, and non-linear effects.

---

## Repository Structure
  TODO: File-structure of REPO
---

## Methodology

### Data Sources
- **NBA Draft Combine Data**: Physical measurements and athletic testing results  
  - Height, weight, wingspan, standing reach  
  - Vertical leap, sprint speed, agility drills  
  - Body fat percentage  
- **NBA Player Performance Data**:
  - Points, rebounds, assists, minutes played  
  - Shooting percentages and usage-related statistics  

Datasets are merged using player name matching, with careful handling of duplicates and inconsistencies.

---

## Data Processing

### Missing Value Handling
- Combine metrics contain substantial missing values
- **KNN Imputation** applied across *all numeric columns with missing data*
- Ensures a fully populated feature matrix for downstream modeling

### Feature Engineering
- Standardized physical metrics
- Derived ratios and composite athletic indicators
- Separation of:
  - **Combine-only features**
  - **Performance targets**

### Handling Multi-Collinearity
- **Variance Inflation Factor (VIF)** used for regression diagnostics
- Identifies redundant or highly correlated predictors
- Guides feature selection for interpretable linear models

---

## Models

### 1. Linear Regression (OLS)
- TODO: Check that this is correct
- Baseline statistical model for interpretability
- Estimated using `statsmodels`
- Provides:
  - Coefficient estimates
  - Confidence intervals
  - Statistical significance tests
- Used to analyze marginal effects of physical attributes on performance

---

### 2. Classification and Regression Trees
- Captures non-linear interactions between athletic traits
- TODO: Tuned for:
  - `max_depth`
  - `min_samples_split`
  - `min_samples_leaf`
- Trees are visualized to interpret key decision splits

---

### 3. Random Forest
- Ensemble model to improve predictive performance
- Reduces overfitting relative to single trees
- Used for:
  - Predicting **PTS** and **REB**
  - Feature importance ranking
- Hyperparameters tuned via cross-validation

---

## Evaluation Metrics

- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **Out-of-Sample R²**
- Model comparison across:
  - Regression vs tree-based methods
  - Points vs rebounds prediction tasks

---

## Key Questions Explored

- Which combine metrics are most predictive of NBA scoring and rebounding?
- Do tree-based models significantly outperform linear regression?
- Are physical measurements more informative for rebounds than points?
- How much predictive power exists *before* any NBA game data is observed?

---

## Getting Started

### Prerequisites
```python
numpy
pandas
scikit-learn
statsmodels
matplotlib
seaborn
