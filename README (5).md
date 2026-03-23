#  Customer Churn Prediction — Bank Customers

A machine learning project to identify bank customers who are likely to leave, using the **Churn Modelling Dataset** from Kaggle.

---

## Objective

Build a supervised classification model that predicts whether a bank customer will churn (leave the bank), and analyze which features drive that decision.

---

##  Dataset

**Source:** [Kaggle — Churn Modelling Dataset](https://www.kaggle.com/datasets/shubh0799/churn-modelling)

**File:** `Churn_Modelling.csv`

| Column | Description |
|--------|-------------|
| `RowNumber` | Row index (dropped) |
| `CustomerId` | Unique customer ID (dropped) |
| `Surname` | Customer surname (dropped) |
| `CreditScore` | Customer credit score |
| `Geography` | Country: France / Spain / Germany |
| `Gender` | Male / Female |
| `Age` | Customer age |
| `Tenure` | Years with the bank |
| `Balance` | Account balance |
| `NumOfProducts` | Number of bank products held |
| `HasCrCard` | Has credit card? (1/0) |
| `IsActiveMember` | Active member? (1/0) |
| `EstimatedSalary` | Estimated annual salary |
| `Exited` | **Target** — Churned (1) or Stayed (0) |

> **10,000 rows** | **Churn rate: ~20.4%**

---

##  Getting Started (Google Colab)

1. Go to [colab.research.google.com](https://colab.research.google.com)
2. Click **File → Upload notebook** and select `Churn_Prediction.ipynb`
3. In the left sidebar, click the ** Files icon ** and upload `Churn_Modelling.csv`
4. Click **Runtime → Run all**

> All required libraries (pandas, scikit-learn, matplotlib, seaborn) come pre-installed in Colab.

---

##  Project Steps

### Step 1 — Import Libraries
Imports `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn` components.

### Step 2 — Load & Explore Data
- Loads the CSV and inspects shape, dtypes, and summary statistics
- Visualizes the class distribution (churn vs. stayed)

### Step 3 — Data Cleaning
- Drops non-predictive columns: `RowNumber`, `CustomerId`, `Surname`
- Checks for missing values and duplicates (none found in this dataset)

### Step 4 — Encode Categorical Features

| Column | Encoding | Reason |
|--------|----------|--------|
| `Gender` | Label Encoding | Binary (Male/Female) — safe to encode as 0/1 |
| `Geography` | One-Hot Encoding | 3 categories — avoids implying a false numeric order |

### Step 5 — Feature/Target Split & Scaling
- Separates features (`X`) from the target (`y = Exited`)
- Applies an **80/20 train-test split** with stratification
- Scales features using `StandardScaler`

### Step 6 — Train Classification Model
- **Model:** `RandomForestClassifier` (100 trees, `class_weight='balanced'`)
- `class_weight='balanced'` handles the class imbalance (~80% stayed vs. ~20% churned)

### Step 7 — Evaluate Model Performance
- **Accuracy:** ~83.80%
- **ROC-AUC:** ~0.8615
- Outputs: Classification Report, Confusion Matrix, ROC Curve

### Step 8 — Feature Importance Analysis
- Bar chart showing importance score of each feature
- KDE / bar plots comparing the top 3 features between churned and stayed customers

---

##  Results

| Metric | Score |
|--------|-------|
| Accuracy | **83.80%** |
| ROC-AUC | **0.8615** |
| F1-Score (Churned) | **0.62** |

---

##  Key Business Insights

| Feature | Finding |
|---------|---------|
| **Age** | Older customers churn more — target retention at middle-aged segments |
| **NumOfProducts** | Customers with only 1 product are high-risk — cross-sell to retain them |
| **IsActiveMember** | Inactive members churn significantly more — run re-engagement campaigns |
| **Balance** | High-balance inactive customers are the most valuable to retain |

---

##  Skills Demonstrated

- Categorical data encoding (Label Encoding & One-Hot Encoding)
- Supervised classification modelling
- Model evaluation (Accuracy, F1, ROC-AUC, Confusion Matrix)
- Feature importance interpretation

---

##  File Structure

```
├── Churn_Prediction.ipynb   # Main Jupyter notebook
├── Churn_Modelling.csv      # Dataset (download from Kaggle)
└── README.md                # This file
```

---

##  Optional Improvements

- **Cross-validation** — Use k-fold CV for more reliable performance estimates
- **Hyperparameter tuning** — Use `GridSearchCV` to optimize Random Forest parameters
- **Try other models** — Compare with XGBoost, Logistic Regression, or Neural Networks
- **SMOTE** — Oversample the minority class for better recall on churned customers
- **SHAP values** — Use the `shap` library for more explainable feature importance
