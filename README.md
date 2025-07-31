# Trilytics-25-Analytics-Case-Competition
# 🌾 Farmer Income Prediction (LTF Challenge)

A machine learning pipeline to predict Indian farmers’ total annual income using demographic, agricultural, and regional features.

> 🏆 Final MAPE: **9.52%**  
> 📁 Submission File: `RJ_predictions.csv`

---

## 📌 Problem Statement

Given a dataset containing socio-economic and farming-related attributes of Indian farmers, predict their **total annual income**. The output is evaluated using the **Mean Absolute Percentage Error (MAPE)**.

---

## 📊 Dataset Overview

- **TrainData:** Contains features and the target variable (`Total Income`)
- **TestData:** Contains the same features but without the target
- **Dictionary:** A sheet explaining the meaning of each column

---
## 🔍 Exploratory Data Analysis (EDA)

### 1. Distribution of Target Variable
![Income Distribution](images/income_distribution.png)

### 2. Boxplot by Region
![Boxplot Region](images/income_by_region.png)

### 3. Scatterplot: Land Holding vs Income
![Scatterplot](https://drive.google.com/uc?id=1rXCZESDFbWUBkM95uMjeASukHfFbqNA_)

---

## 🔬 Data Cleaning

- ✅ Handled missing values using median for numerical, `'Unknown'` for categorical
- ✅ Removed duplicate records
- ✅ Generated an interactive profiling report using `ydata-profiling`

---

## 🧪 Feature Engineering

- 📏 Scaled numeric features using `StandardScaler`
- 🔠 Encoded categorical features using `OneHotEncoder`
- 📉 Reduced noise using **RFE (Recursive Feature Elimination)**

---

## 🤖 Models Trained (Total: 9)

| Model                | Tuned? | Notes                                |
|---------------------|--------|--------------------------------------|             |
| Random Forest        | ✅ Yes | GridSearch on depth & trees         |
| XGBoost              | ✅ Yes | GridSearch on `n_estimators`, `lr`  |
| LightGBM             | ✅ Yes | GridSearch on `num_leaves`, `lr`    |
| CatBoost             | No     | Fast, no encoding required          |
| Voting Regressor     | Yes    | Combined top 3 models               |
| Stacking Regressor   | Yes    | Linear meta-model on base learners  |

---

## 🔧 Model Evaluation

- Validation strategy: **Train/Validation Split (80/20)**
- Primary metric: **Mean Absolute Percentage Error (MAPE)**

### 🔝 Best Models (Validation MAPE)

| Model          | MAPE (%) |
| XGBoost        | 7     |
| LightGBM       | 10.7     |
| CatBoost       | 15.4     |


---

## 🧠 Final Model: Weighted Ensemble

Combined predictions from XGBoost, LightGBM, and Voting using weighted average:


Tech Stack
Python 3.10

scikit-learn

pandas, numpy

seaborn, matplotlib

xgboost, lightgbm, catboost

ydata-profiling

---

PRESENTATION (TeamName_presentation.pdf)

Slides include:

Introduction

EDA findings

Missing value & outlier handling

Feature transformations

Model evaluation

Final results

Suggestions & future work



