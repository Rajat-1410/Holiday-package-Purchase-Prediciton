# Holiday Package Purchase Prediction

## Project Overview

This project focuses on predicting whether a customer will purchase a holiday package (`ProdTaken`) using historical customer data. The goal is to **identify high-potential customer segments** so that marketing efforts can be targeted efficiently, reducing cost and improving conversion rates.

The project is implemented end-to-end in **Python (Jupyter Notebook)** and demonstrates a complete **data science workflow**: from data understanding and preprocessing to model building, evaluation, and business insights.

---

##  Business Problem

A travel company offers holiday packages to customers through sales pitches. However, not all customers convert. The company wants to:

* Predict which customers are most likely to purchase a holiday package
* Understand key factors influencing purchase decisions
* Optimize marketing and sales outreach using data-driven insights

This is framed as a **binary classification problem**.

---

Dataset Description

The dataset contains customer demographic, behavioral, and interaction-related features such as:

* Customer demographics (Age, Gender, MaritalStatus)
* Engagement details (DurationOfPitch, NumberOfFollowups)
* Travel behavior (NumberOfTrips, PreferredPropertyStar)
* Financial indicators (MonthlyIncome)
* Target variable: `ProdTaken` (0 = Not Purchased, 1 = Purchased)

---

##  Tools & Libraries Used

* Python 3
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* Jupyter Notebook

---
 Project Workflow

### 1. Data Understanding & Exploration

* Loaded and inspected the dataset
* Checked data types, missing values, and basic distributions
* Identified numerical and categorical features

### 2. Missing Value Analysis

* Numerical features: handled using **median imputation**
* Categorical features: handled using **most frequent value imputation**
* Reasoning: median is robust to outliers; mode preserves category meaning

### 3. Feature Engineering

* Categorical variables encoded using **OneHotEncoder**
* Numerical variables scaled using **StandardScaler**
* Implemented using **ColumnTransformer** for clean and reproducible preprocessing

> Note: Scaling is essential for Logistic Regression but not strictly required for tree-based models. It was applied uniformly for pipeline consistency.

### 4. Train-Test Split

* Data split into training and test sets
* Stratified split used to preserve class distribution

5. Model Building

The following models were trained and evaluated:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier

6. Model Evaluation

Multiple evaluation metrics were used:

* Accuracy
* Precision
* Recall
* F1-score
* ROC–AUC

ROC curves were plotted to visually compare model performance.
---
ROC Curve Analysis

* Random Forest produced a smooth ROC curve due to ensemble averaging
* Decision Tree showed step-like behavior due to discrete probability outputs
* Logistic Regression showed moderate smoothness

This behavior is expected and reflects model structure rather than an error.

---
 Key Insights

* Customers with higher engagement (longer pitch duration, more follow-ups)
* Customers with higher income and frequent travel history
* Certain demographic segments showed higher conversion probability

These features were identified using **feature importance from Random Forest**.

---
 Business Recommendations

* Use the Random Forest model to score customers weekly
* Target the top 20–30% high-probability customers for outreach
* Focus sales efforts on customers with strong engagement indicators
* Monitor lift compared to random targeting

---
 Future Improvements

* Hyperparameter tuning using GridSearchCV
* Handle class imbalance using SMOTE or class weights
* Add Precision–Recall curves for imbalanced analysis
* Model calibration analysis
* Deploy as an API using Flask/FastAPI

---
Repository Structure

```
├── random_forest_notebook.ipynb
├── Travel.csv
├── auc.png
├── README.md
```

---

Key Takeaways

This project demonstrates:

* Strong understanding of classification metrics
* Proper preprocessing using sklearn pipelines
* Correct handling of ROC–AUC and probability-based evaluation
* Translation of ML results into business insights

---

 Author

**Rajat Singh**
MSc Statistics | Aspiring Data Scientist

---

 If you found this project useful, feel free to star the repository!
