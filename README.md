# CreditWise – Loan Approval Prediction

## Project Overview

CreditWise is a Machine Learning classification project developed to predict loan approval outcomes based on applicants' personal, financial, employment, and credit-related information.

The project is based on a business scenario involving SecureTrust Bank, a financial institution in India that wants to improve its traditional manual loan verification process.

Manual loan evaluation can be time-consuming and inconsistent. The goal of this project is to build a data-driven prediction model that helps identify loan applications as Approved or Rejected using historical applicant information.

## Business Problem

SecureTrust Bank faces two major challenges:

- Good customers sometimes get rejected, resulting in lost business opportunities.
- High-risk customers sometimes get approved, potentially leading to financial losses.

This project explores how Machine Learning can support more efficient and consistent loan approval decisions.

## Project Objectives

- Perform data cleaning and preprocessing.
- Conduct Exploratory Data Analysis (EDA).
- Identify patterns and relationships between applicant features and loan approval.
- Apply categorical encoding and numerical feature scaling.
- Train and compare multiple classification algorithms.
- Perform feature engineering to improve model performance.
- Evaluate models using classification metrics.

## Dataset Description

The dataset contains loan applicant information, including:

| Feature | Description |
|---|---|
| Applicant_ID | Unique applicant identifier |
| Applicant_Income | Monthly applicant income |
| Coapplicant_Income | Monthly co-applicant income |
| Employment_Status | Employment category |
| Age | Applicant age |
| Marital_Status | Marital status |
| Dependents | Number of dependents |
| Credit_Score | Credit bureau score |
| Existing_Loans | Number of existing loans |
| DTI_Ratio | Debt-to-Income ratio |
| Savings | Applicant savings balance |
| Collateral_Value | Value of collateral |
| Loan_Amount | Requested loan amount |
| Loan_Term | Loan duration in months |
| Loan_Purpose | Purpose of the loan |
| Property_Area | Urban / Semi-Urban / Rural |
| Education_Level | Applicant education level |
| Gender | Applicant gender |
| Employer_Category | Employer category |
| Loan_Approved | Target variable (1 = Approved, 0 = Rejected) |

## Technologies & Libraries

- **Programming Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn
- **Development Environment:** Jupyter Notebook

## Project Workflow

### 1. Data Preprocessing
- Loaded the dataset using Pandas.
- Inspected dataset structure, data types, missing values, and descriptive statistics.
- Handled missing numerical values using mean imputation.
- Handled missing categorical values using most-frequent imputation.
- Removed the Applicant_ID column.

### 2. Exploratory Data Analysis (EDA)

Performed visual analysis to understand applicant characteristics and loan approval patterns.

Explorations included:
- Loan approval distribution.
- Gender and education distribution.
- Employment and marital status.
- Loan purpose and property area.
- Applicant and co-applicant income distributions.
- Relationship between loan approval and income, credit score, DTI ratio, savings, age, and loan amount.
- Correlation analysis using a heatmap.

### 3. Data Encoding
- Applied Label Encoding to Education_Level and Loan_Approved.
- Applied One-Hot Encoding to categorical features.
- Used `drop="first"` to reduce redundant encoded columns.

### 4. Train-Test Split and Feature Scaling
- Split the dataset into 80% training and 20% testing.
- Used `random_state=42` for reproducibility.
- Applied StandardScaler to numerical model inputs.

### 5. Model Training

Implemented and compared three classification algorithms:

**Logistic Regression**
- Used as a baseline classification model.

**K-Nearest Neighbors (KNN)**
- Used to classify applicants based on nearby data points.
- Set `n_neighbors=5`.

**Gaussian Naive Bayes**
- Applied probabilistic classification based on Bayes' theorem.

### 6. Model Evaluation

Evaluated models using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

### 7. Feature Engineering

Created two additional features:

- `DTI_Ratio_sq` – Squared Debt-to-Income Ratio.
- `Credit_Score_sq` – Squared Credit Score.

Retrained and evaluated all three classification models to compare their performance after feature engineering.

## Model Performance

### Initial Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 86.50% | 78.33% | 77.05% | 77.69% |
| KNN | 76.00% | 62.75% | 52.46% | 57.14% |
| Naive Bayes | 86.50% | 80.36% | 73.77% | 76.92% |

### Model Comparison After Feature Engineering

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 87.50% | 79.03% | 80.33% | 79.67% |
| KNN | 75.50% | 62.00% | 50.82% | 55.86% |
| Naive Bayes | 86.50% | 78.33% | 77.05% | 77.69% |

### Best Performing Model

**Logistic Regression after Feature Engineering**

- Accuracy: 87.50%
- Precision: 79.03%
- Recall: 80.33%
- F1-Score: 79.67%

Feature engineering improved Logistic Regression's performance, particularly its recall and F1-score.

Based on the balance between precision and recall, Logistic Regression after feature engineering achieved the best overall F1-score among the tested models.

## Key Learnings

Through this project, I gained practical experience in:

- Data cleaning and missing-value imputation.
- Exploratory Data Analysis and data visualization.
- Label Encoding and One-Hot Encoding.
- Feature scaling using StandardScaler.
- Training and comparing classification algorithms.
- Evaluating models using precision, recall, F1-score, and confusion matrices.
- Feature engineering and model performance comparison.

## Future Improvements

- Perform hyperparameter tuning to optimize model performance.
- Use cross-validation for more reliable model evaluation.
- Apply feature importance and model interpretability techniques.
- Evaluate model fairness across different applicant groups.
- Build an interactive loan approval prediction application.
- Explore additional classification algorithms.

## Conclusion

CreditWise demonstrates how Machine Learning can be applied to a real-world banking problem through data preprocessing, exploratory analysis, classification, and feature engineering.

Among the three tested algorithms, Logistic Regression after feature engineering achieved the highest F1-score of 79.67% and accuracy of 87.50%.

The project highlights the importance of comparing multiple models and evaluating performance beyond accuracy alone.

**Project Category:** Machine Learning | Supervised Learning | Binary Classification

**Domain:** Banking and Financial Services