# 🏦 Beta Bank Customer Churn Prediction

A machine learning project focused on predicting customer churn at **Beta Bank** using classification algorithms and class balancing techniques. The goal is to identify customers who are at risk of leaving the bank and support data-driven retention strategies.

---

## 📋 Project Overview

Customer retention is often more cost-effective than acquiring new customers. For this reason, Beta Bank aims to identify customers who are likely to terminate their relationship with the bank before they actually leave.

This project evaluates several machine learning models and balancing techniques to build an effective churn prediction system.

---

## 🎯 Objective

Develop a machine learning model capable of predicting whether a customer will leave the bank (**Exited = 1**) or remain a customer (**Exited = 0**).

The project focuses on:

- Data preparation and feature engineering.
- Handling missing values.
- Addressing class imbalance.
- Training and tuning multiple classification models.
- Evaluating model performance using appropriate metrics.
- Selecting the best model based on predictive performance.

---

## 📊 Dataset

The dataset contains customer information including:

- Credit score
- Geography
- Gender
- Age
- Tenure
- Account balance
- Number of products
- Credit card ownership
- Active membership status
- Estimated salary

### Target Variable

| Value | Meaning |
|---------|---------|
| 0 | Customer remains with the bank |
| 1 | Customer leaves the bank |

---

## 🛠 Data Preparation

The following preprocessing steps were applied:

### Data Cleaning

- Removed irrelevant features:
  - `RowNumber`
  - `CustomerId`
  - `Surname`

### Missing Values

- Missing values in `Tenure` were imputed to preserve the dataset.

### Feature Encoding

- Categorical variables were converted into numerical representations using **One-Hot Encoding**.

### Feature Scaling

- Features were scaled to support models that are sensitive to feature magnitude, such as **Logistic Regression**.

---

## ⚖️ Class Imbalance

The dataset presented a significant class imbalance:

- Approximately **80%** retained customers.
- Approximately **20%** churned customers.

To address this issue, three different scenarios were evaluated:

1. **Imbalanced Dataset**
2. **Class Weight Balancing**
3. **Oversampling**

### Note

An attempt was made to use **SMOTE (Synthetic Minority Oversampling Technique)** from the `imblearn` library. However, installation restrictions on the platform prevented the required package from being installed. Therefore, a traditional oversampling approach was implemented instead.

---

## 🤖 Models Evaluated

### Decision Tree Classifier

Hyperparameter tuning:

- `max_depth`

### Random Forest Classifier

Hyperparameter tuning:

- `max_depth`
- `n_estimators`

### Logistic Regression

Hyperparameter tuning:

- `C`
- `solver`

---

## 📈 Evaluation Metrics

The models were evaluated using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**
- **ROC-AUC**

Special attention was given to:

- **Recall**, because correctly identifying customers who are likely to leave is critical.
- **F1 Score**, because it balances precision and recall.
- **ROC-AUC**, because it measures the model's ability to distinguish between churned and retained customers.

---

## 🏆 Best Model

The best-performing model was:

### Random Forest Classifier

Optimal hyperparameters:

```python
max_depth = 13
n_estimators = 100
```

Training strategy:

```python
Oversampling
```

---

## ✅ Final Test Results

| Metric | Score |
|----------|----------:|
| Accuracy | **0.97** |
| Precision | **0.89** |
| Recall | **0.98** |
| F1 Score | **0.93** |
| ROC-AUC | **1.00** |

---

## 🔍 Key Findings

- Class imbalance significantly reduced the models' ability to detect churn cases.
- Class weighting improved recall but reduced overall accuracy.
- Oversampling produced the best balance between precision and recall.
- Random Forest consistently outperformed Decision Tree and Logistic Regression.
- The final model achieved a recall of **0.98**, successfully identifying nearly all customers at risk of leaving.
- The final model achieved an F1 Score of **0.93**, demonstrating strong overall classification performance.

---

## 📉 ROC Curve

The final Random Forest model achieved a **ROC-AUC score of 1.00**, indicating an exceptional ability to distinguish between customers who will churn and those who will remain.

---

## 🚀 Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Plotly Express
- Jupyter Notebook

---

## 📁 Repository Structure

```text
├── data/
├── notebooks/
│   └── churn_prediction.ipynb
├── images/
├── README.md
└── requirements.txt
```

---

## 🎓 Conclusion

This project demonstrates the importance of addressing class imbalance in churn prediction problems. By combining oversampling with a carefully tuned Random Forest model, it was possible to build a highly effective classification system capable of accurately identifying customers at risk of leaving the bank.

The final model exceeded the project's performance requirements and provides a valuable tool for supporting customer retention initiatives through data-driven decision making.
