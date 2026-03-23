# Insurance Claim Prediction using Linear Regression

## Introduction
This project focuses on predicting medical insurance charges based on various personal and lifestyle factors such as age, BMI, smoking habits, and more. The goal is to build a regression model that can estimate insurance costs accurately and help understand the key factors influencing these charges.

This project is ideal for beginners in machine learning and data analysis, as it covers the complete pipeline from data exploration to model evaluation.

## Objective
- To estimate medical insurance charges using Linear Regression
- To analyze the impact of features like age, BMI, and smoking status
- To evaluate model performance using standard error metrics

## Skills and Concepts Covered
- Regression Modeling (Linear Regression)
- Exploratory Data Analysis (EDA)
- Data Visualization
- Feature Encoding (Label Encoding)
- Model Evaluation (MAE, RMSE, R² Score)

## Dataset
The dataset used is insurance.csv, which contains the following features:

- age: Age of the individual
- sex: Gender
- bmi: Body Mass Index
- children: Number of children
- smoker: Smoking status (Yes/No)
- region: Residential area
- charges: Medical insurance cost (Target)

## Project Workflow

### Import Libraries
Essential libraries used include pandas, numpy, matplotlib, seaborn, and sklearn.

### Load Dataset
The dataset is loaded using pandas and initially inspected for structure and data types.

### Exploratory Data Analysis (EDA)
Missing values are checked and distributions of variables are analyzed to understand the data.

### Data Visualization
Various plots are used to explore relationships between features and insurance charges.

### Data Preprocessing
Categorical variables are converted using Label Encoding to prepare the data for modeling.

### Model Building
The dataset is split into training and testing sets and a Linear Regression model is applied.

### Model Evaluation
Model performance is evaluated using MAE, RMSE, and R² Score.

## Insights
- Smoking has the biggest impact on insurance charges, with smokers paying significantly higher premiums.
- Age is positively correlated with charges, meaning older individuals tend to have higher costs.
- BMI also influences charges, especially at higher values.
- Number of children has a smaller effect compared to other features.
- Region and gender have relatively less impact on charges.

## Results
The Linear Regression model provides a reasonable prediction of insurance costs. The model captures general trends, though more complex models may improve performance.

## Future Improvements
- Apply advanced models such as Random Forest, Decision Tree, and Gradient Boosting
- Perform feature engineering
- Handle outliers more effectively
- Experiment with scaling techniques

## Conclusion
This project demonstrates how machine learning can be used to predict real-world financial outcomes like insurance costs. It highlights the importance of data analysis, feature understanding, and model evaluation. While Linear Regression provides a solid baseline, further improvements can enhance prediction accuracy.
