# Titanic Survival Prediction - CS 422 Final Project

##  Project Overview
This project is part of the **CS 422 Course Project** , aiming to apply data mining techniques to a real-world predictive modeling problem. The Titanic dataset was used to build a classification model that predicts whether a passenger survived the infamous Titanic disaster based on available features.


##  Problem Statement
Given the passenger data (such as age, sex, ticket class, and number of siblings/spouses aboard), predict whether a passenger survived (1) or not (0). This is a **supervised binary classification problem**.


##  Methodology Summary

### 1. **Data Preprocessing**
- Dropped irrelevant columns: `PassengerId`, `Name`, `Ticket`
- Imputed missing values:
  - Numeric: median
  - Categorical: most frequent
- Standardized numerical features
- One-hot encoded categorical variables
- Engineered new features:
  - `FamilySize = SibSp + Parch + 1`
  - `IsAlone = 1` if `FamilySize == 1` else `0`

### 2. **Modeling**
- Primary model: **Random Forest Classifier**
- Baseline models: **Logistic Regression**, **Support Vector Machine (SVM)**
- Hyperparameter tuning via **GridSearchCV** (5-fold cross-validation)
- Evaluation metrics:
  - Accuracy
  - ROC-AUC
  - Confusion Matrix
  - Feature Importance
  - ROC Curve


##  Key Results

| Model              | Accuracy | ROC-AUC |
|-------------------|----------|---------|
| Random Forest      | 0.8045    | 0.8431   |
| Logistic Regression| 0.8045    | 0.8267   |
| SVM                | 0.8212    | 0.8372   |

- `Random Forest` performed best overall and was chosen as the final model.
- Key features: `Sex`, `Fare`, `Age`, `Pclass`, `IsAlone`, `Embarked_C`


