# Chronic Kidney Disease Detection using Ensemble Machine Learning

## Overview

This project implements and reproduces the methodology proposed in the paper **"Machine Learning Models for Chronic Kidney Disease Diagnosis and Prediction"** (Biomedical Signal Processing and Control, 2024).

The objective is to accurately predict the presence of Chronic Kidney Disease (CKD) using clinical and laboratory measurements. The implementation follows the paper's preprocessing and modeling pipeline, including advanced missing-value imputation, class balancing, feature selection, and ensemble learning techniques.

## Key Features

* Missing value handling using **MICE (Multiple Imputation by Chained Equations)**
* Class imbalance correction using **Borderline-SMOTE**
* Feature selection using:

  * Recursive Feature Elimination (RFE)
  * Boruta Feature Selection
* Hyperparameter optimization using Randomized Search CV
* Multiple ensemble learning models:

  * Random Forest
  * AdaBoost
  * Bagging
  * Voting Classifier
  * Gradient Boosting
  * XGBoost
  * LightGBM
  * Stacking Classifier
* Comprehensive model evaluation using:

  * Accuracy
  * Precision
  * Recall
  * F1 Score
  * ROC-AUC

## Dataset

The project uses the **Chronic Kidney Disease Dataset** from the UCI Machine Learning Repository.

### Dataset Statistics

* Total Samples: 400
* Features: 24 Clinical Attributes
* Classes:

  * CKD
  * Not CKD

### Example Features

* Age
* Blood Pressure
* Specific Gravity
* Albumin
* Blood Glucose Random
* Blood Urea
* Serum Creatinine
* Hemoglobin
* Packed Cell Volume
* Hypertension
* Diabetes Mellitus

## Methodology

### 1. Data Preprocessing

* Replace categorical missing values with dedicated categories.
* Apply MICE imputation for numerical attributes.
* Encode categorical variables.
* Standardize numerical features.

### 2. Feature Selection

Two feature selection techniques are implemented:

#### Recursive Feature Elimination (RFE)

Selects the most informative subset of features by recursively removing less important attributes.

#### Boruta Feature Selection

Random Forest–based wrapper method that identifies statistically significant features.

### 3. Class Balancing

The CKD dataset is imbalanced.

To address this issue:

* Borderline-SMOTE is applied only on the training set.
* Synthetic samples are generated near decision boundaries.

### 4. Model Training

The following ensemble models are trained and evaluated:

* Random Forest
* Voting Classifier
* Bagging Classifier
* AdaBoost
* Gradient Boosting Decision Tree (GBDT)
* XGBoost
* LightGBM
* Stacking Classifier

### 5. Hyperparameter Optimization

RandomizedSearchCV is used to identify optimal model configurations.

## Results

The reproduced implementation demonstrates strong predictive performance for CKD diagnosis.

Best-performing models:

| Model              | Accuracy |
| -------------      | -------- |
| Gradient boost     | 98.75    |
| AdaBoost           | 98.75    |
| Random Forest      | 98.75    |
| Bagging            | 98.75    |

mean accuracy: 98.6<br>
final accuracy(after tuning): 98.75<br>
Performance may vary slightly depending on preprocessing choices, train-test splits, and random seeds.

## Tech Stack

* Python
* Pandas
* NumPy
* Scikit-Learn
* Imbalanced-Learn
* XGBoost
* LightGBM
* Matplotlib
* Seaborn

## Research Paper

This implementation is based on:

**Rahman, M. M., Al-Amin, M. A., & Hossain, J.**
*"Machine Learning Models for Chronic Kidney Disease Diagnosis and Prediction"*
Biomedical Signal Processing and Control, 2024.

## Disclaimer

This project is intended for educational and research purposes only and should not be used as a substitute for professional medical diagnosis.
