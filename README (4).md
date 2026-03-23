#  Loan Default Prediction — Credit Risk Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-green?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

##  Project Overview

This project predicts whether a loan applicant will **default on their loan** using machine learning. It covers the full data science workflow — from data loading and EDA to model training and evaluation.

> **Target Variable:** `Default` — `1` = Defaulted, `0` = Did Not Default

---

##  Dataset

| Property | Details |
|---|---|
| **File** | `Loan_default.csv` |
| **Rows** | 255,347 |
| **Columns** | 18 |
| **Missing Values** | None |
| **Default Rate** | ~11.6% |

### Features Used

| Feature | Type | Description |
|---|---|---|
| Age | Numerical | Applicant's age |
| Income | Numerical | Annual income ($) |
| LoanAmount | Numerical | Loan amount requested ($) |
| CreditScore | Numerical | Applicant's credit score |
| MonthsEmployed | Numerical | Months of employment |
| NumCreditLines | Numerical | Number of credit lines |
| InterestRate | Numerical | Loan interest rate (%) |
| LoanTerm | Numerical | Loan term (months) |
| DTIRatio | Numerical | Debt-to-Income ratio |
| Education | Categorical | High School / Bachelor's / Master's / PhD |
| EmploymentType | Categorical | Full-time / Part-time / Self-employed / Unemployed |
| MaritalStatus | Categorical | Single / Married / Divorced |
| HasMortgage | Categorical | Yes / No |
| HasDependents | Categorical | Yes / No |
| LoanPurpose | Categorical | Auto / Business / Education / Home / Other |
| HasCoSigner | Categorical | Yes / No |

---

##  Technologies Used

- **Python 3**
- **Pandas** — Data loading and manipulation
- **NumPy** — Numerical operations
- **Matplotlib & Seaborn** — Data visualization
- **Scikit-Learn** — Machine learning model and evaluation

---

##  Project Workflow

### 1 Data Loading & Inspection
- Loaded dataset with 255,347 rows and 18 columns
- Inspected shape, column names, data types
- Verified zero missing values across all columns

### 2 Exploratory Data Analysis (EDA)
- **Default Distribution** — Bar chart and pie chart showing class imbalance
- **Loan Amount** — Histogram and box plot by default status
- **Education** — Grouped bar chart and stacked percentage chart
- **Income** — Overlapping histogram and box plot by default status

### 3 Data Preprocessing
- Dropped `LoanID` (unique identifier, no predictive value)
- Encoded all categorical columns using `LabelEncoder`
- Split data: **80% training / 20% testing** with stratification

### 4 Model Training
- Model: **Logistic Regression**
- Solver: `saga` (optimized for large datasets)
- Applied `StandardScaler` for feature normalization
- Used all CPU cores (`n_jobs=-1`) for faster training

### 5 Model Evaluation
- **Accuracy Score**
- **Confusion Matrix** with True/False Positive and Negative breakdown

---

##  Results

| Metric | Value |
|---|---|
| **Model** | Logistic Regression |
| **Test Accuracy** | 88.51% |
| **Correct Predictions** | 45,202 / 51,070 |
| **Misclassified** | 5,868 / 51,070 |
| **True Negatives (TN)** | 45,018 |
| **False Positives (FP)** | 121 |
| **False Negatives (FN)** | 5,747 |
| **True Positives (TP)** | 184 |

---

##  Key Insights

- **Loan Amount** — Defaulters tend to borrow larger loan amounts
- **Income** — Lower income applicants are more likely to default
- **Education** — Education level has minimal effect on default rate
- The dataset is **imbalanced** — only ~11.6% of applicants defaulted

