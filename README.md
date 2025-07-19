# 🚨 Fraudulent Transaction Detection using Random Forest

This project aims to detect fraudulent transactions for a financial company using machine learning. Leveraging a large-scale dataset of over **6.3 million** transactions, we applied a **Random Forest Classifier** to achieve a **99.8% accuracy** in identifying fraudulent activities. Insights gained from the model were used to create an actionable risk-reduction plan for the company.

---

## 📁 Dataset

- **Format**: CSV  
- **Size**: 6,362,620 rows × 10 columns  
- **Columns**:
  - `step`: Time step (hour)
  - `type`: Transaction type
  - `amount`: Transaction amount
  - `nameOrig`: Customer ID
  - `oldbalanceOrg`: Original balance of sender
  - `newbalanceOrig`: New balance of sender
  - `nameDest`: Recipient ID
  - `oldbalanceDest`: Original balance of recipient
  - `newbalanceDest`: New balance of recipient
  - `isFraud`: 1 if transaction is fraud, else 0

---

## 🎯 Objectives

- Build a high-performance fraud detection model.
- Analyze the data to uncover fraud-related patterns.
- Create actionable business strategies to mitigate fraud.

---

## 🧠 Machine Learning Model

- **Algorithm**: Random Forest Classifier  
- **Accuracy**: **99.8%**  
- **Why Random Forest?**  
  - Excellent for handling large datasets  
  - Robust to outliers and noise  
  - Provides feature importance for interpretability

---

## 🧪 EDA & Feature Engineering

- Removed non-informative features: `nameOrig`, `nameDest`
- Converted categorical `type` feature using Label Encoding
- Identified strong indicators of fraud (e.g. high `amount`, `type == TRANSFER` or `CASH_OUT`)
- Noted that fraud typically occurs in specific transaction types

---

## 🔎 Key Findings

- Most fraud cases are found in **TRANSFER** and **CASH_OUT** transaction types.
- Fraud transactions generally involve **zero balance** updates, i.e., no change in `newbalanceDest`.
- Visualizations show clear separations between fraud and non-fraud behavior for specific features.

---

## 📊 Model Performance

| Metric     | Score     |
|------------|-----------|
| Accuracy   | 99.8%     |
| Precision  | 0.98      |
| Recall     | 0.90      |
| F1-Score   | 0.94      |
| ROC AUC    | 0.99      |

Confusion matrix and ROC curve were used to validate model performance.

---

## 🚀 Actionable Plan

Based on the model's insights, the following steps are recommended:

1. **Transaction Monitoring**: Apply stricter rules for `TRANSFER` and `CASH_OUT` transactions.
2. **Threshold Triggers**: Flag transactions with zero `newbalanceDest` or unexpected balance changes.
3. **User Behavior Tracking**: Monitor frequent or large-amount transactions by the same users.
4. **Model Deployment**: Integrate the model into live systems for real-time fraud detection.

---

## 🛠 Tech Stack

- **Language**: Python 3.x  
- **Libraries**:  
  - `pandas`, `numpy`  
  - `matplotlib`, `seaborn`  
  - `sklearn`  
