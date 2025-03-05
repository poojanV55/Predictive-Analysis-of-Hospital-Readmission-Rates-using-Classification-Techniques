# **Predictive-Analysis-of-Hospital-Readmission-Rates-using-Classification-Techniques**

## **Overview**
This project aims to predict hospital readmission of diabetes patients using machine learning models. The dataset used is the *Diabetes 130-US hospitals* dataset, containing **101,766 samples** and **47 features** collected from various hospitals between **1999-2008**.

## **Problem Statement**
The goal is to determine whether a patient will be readmitted to the hospital based on various medical and demographic features.

## **Dataset**
- **Source**: Diabetes 130-US hospitals dataset (1999-2008)
- **Samples**: 101,766
- **Features**: 47 (including patient demographics, medications, medical conditions, and laboratory results)

## **Data Preprocessing**
### **Handling Missing Data**
- Features with more than 40% missing values (*weight, medical_specialty, payer_code*) were dropped.
- Other missing values were imputed or categorized appropriately.

### **Feature Encoding**
- **Categorical Variables**:
  - One-hot encoding for non-ordinal categorical variables (*race, diagnosis codes*).
  - Label encoding for ordinal categories (*medication changes, age brackets, test results*).
- **Diagnosis Feature Grouping**:
  - Diagnosis codes were categorized into **10 groups** based on the **ICD-9** coding system.

### **Target Variable Transformation**
- Converted readmission categories:
  - 'NO' → **0** (No readmission)
  - '<30' and '>30' → **1** (Readmitted)

## **Modeling & Results**
Several machine learning models were tested, and their performance was evaluated based on **Precision, Recall, F1-Score, and Accuracy**.

| **Model**                | **Accuracy** |
|--------------------------|-------------|
| Naïve Bayes             | 62%         |
| Logistic Regression     | 62%         |
| Decision Tree          | 56%         |
| Support Vector Machine  | 61%         |
| Random Forest         | 64%         |
| Bagging Classifier    | 60%         |
| Neural Network        | 54%         |
| XGBoost Classifier    | **65% (Best)** |
| CatBoost Classifier   | 64%         |

## **Conclusion**
- **XGBoost** performed the best, achieving the highest accuracy and effectively capturing **both linear and non-linear** relationships.
- **Random Forest** and **CatBoost** also performed well, making them viable alternatives.
- Further improvements can be made by **feature engineering**, **hyperparameter tuning**, and **ensemble learning**.

## **Requirements**
To run this project, install the following dependencies:

```bash
pip install pandas numpy scikit-learn xgboost catboost matplotlib seaborn
