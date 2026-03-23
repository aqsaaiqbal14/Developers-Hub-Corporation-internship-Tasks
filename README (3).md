#  Iris Dataset — Exploratory Data Analysis & Classification

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3-red?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

##  Task Objective

Perform a complete **Exploratory Data Analysis (EDA)** on the famous **Iris dataset**, then train and evaluate a machine learning classification model to predict iris species based on flower measurements.

**Core Goals:**
- Understand the structure and quality of the dataset
- Visualize distributions, relationships, and outliers
- Build and evaluate a K-Nearest Neighbors (KNN) classifier
- Draw meaningful conclusions from data and model results

---

##  Repository Structure

```
iris-eda-classification/
│
├── iris_eda_notebook.ipynb   # Main Jupyter Notebook (full analysis)
├── README.md                 # This file
│
└── plots/                    # Saved visualizations
    ├── scatter_plot.png
    ├── histogram.png
    ├── boxplot.png
    ├── pairplot.png
    ├── heatmap.png
    ├── confusion_matrix.png
    └── knn_k_optimization.png
```

---

##  Dataset Description

The **Iris dataset** is one of the most well-known datasets in machine learning, originally introduced by statistician Ronald Fisher in 1936.

| Property       | Details                                       |
|----------------|-----------------------------------------------|
| Samples        | 150 (50 per species)                          |
| Features       | 4 numerical (sepal/petal length & width)      |
| Target Classes | 3 (Setosa, Versicolor, Virginica)             |
| Missing Values | None                                          |
| Source         | `seaborn.load_dataset('iris')`                |

**Features:**
- `sepal_length` — Length of the sepal in cm
- `sepal_width` — Width of the sepal in cm
- `petal_length` — Length of the petal in cm
- `petal_width` — Width of the petal in cm
- `species` — Target label (setosa / versicolor / virginica)

---

##  My Approach

### Step 1 — Data Loading & Inspection
- Loaded dataset using `seaborn`
- Inspected shape, column types, and statistical summary
- Verified class balance (50 samples each)

### Step 2 — Data Cleaning
- Checked for missing values → **None found**
- Checked for duplicate rows → **3 duplicates removed**
- Encoded target labels numerically for model compatibility

### Step 3 — Exploratory Data Analysis
Created 5 types of visualizations:

| Chart | Purpose |
|---|---|
| **Scatter Plot** | Identify clusters and relationships between features |
| **Histogram** | Understand distribution shape per species |
| **Box Plot** | Detect outliers and compare value spread |
| **Pair Plot** | Visualize all pairwise feature combinations |
| **Correlation Heatmap** | Quantify inter-feature relationships |

### Step 4 — Model Training
- Algorithm: **K-Nearest Neighbors (KNN)**
- Split: 80% training / 20% testing (stratified)
- Hyperparameter tuning: tested k = 1 to 20

### Step 5 — Evaluation
- Accuracy Score
- Classification Report (Precision, Recall, F1-Score)
- Confusion Matrix
- K vs Accuracy optimization curve

---

##  Results & Insights

### Model Performance

| Metric      | Score     |
|-------------|-----------|
| Accuracy    | **~97%**  |
| Best K      | 5–7       |
| Weakest Class | Versicolor (slight overlap with Virginica) |

### Key EDA Insights

1. **Petal features are more powerful than sepal features** for distinguishing species
2. **Setosa** is always clearly separable from the other two species
3. **Versicolor and Virginica** share some overlap in sepal measurements
4. **Petal length and petal width** are highly correlated (r = 0.96)
5. The dataset is **perfectly balanced** — no class imbalance issues
6. **No missing or null values** — minimal data cleaning required

---

##  Technologies Used

| Library         | Purpose                            |
|-----------------|------------------------------------|
| `pandas`        | Data loading, inspection, cleaning |
| `numpy`         | Numerical operations               |
| `matplotlib`    | Base plotting engine               |
| `seaborn`       | Statistical visualizations         |
| `scikit-learn`  | Model training & evaluation        |

---

##  How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/iris-eda-classification.git
   cd iris-eda-classification
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook iris_eda_notebook.ipynb
   ```

4. **Run all cells** — `Kernel → Restart & Run All`

---

##  Author

**AQSA IQBAL**
- Internship Task 1 — Data Science & Machine Learning
- GitHub: [@YOUR_USERNAME](https://github.com/YOUR_USERNAME)



