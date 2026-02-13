# Fraud Transaction Detection using Machine Learning

## Project Overview
Financial fraud is a major challenge for digital payment companies and banks. Fraudulent transactions lead to significant financial losses and reduced customer trust.

This project builds a *machine learning-based fraud detection system** that proactively identifies suspicious transactions using transaction behavior, balance changes, and transaction types.

The goal is to:
- Detect fraudulent transactions accurately
- Reduce financial loss
- Provide actionable business insights
- Suggest prevention strategies

----

##  Dataset Information

The dataset contains:

- 6.3 million transactions
- 10 features
- Binary target → `isFraud`

### Key Columns

| Feature | Description |
|---------|-------------|
| step | Time step (hourly simulation) |
| type | Transaction type (Transfer, Cash-out, etc.) |
| amount | Transaction amount |
| oldbalanceOrg / newbalanceOrig | Sender balances |
| oldbalanceDest / newbalanceDest | Receiver balances |
| isFraud | Fraud label (Target) |

⚠️ Note: Full dataset is not uploaded due to size limits. A small sample can be used for testing.

---

## ⚙️ Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

## 🚀 Project Workflow

### 1️⃣ Data Cleaning
- Checked missing values
- Removed customer IDs (not predictive)
- Log transformation for skewed amounts
- Correlation analysis

### 2️⃣ Feature Engineering
Created new fraud-indicative features:
- Balance differences
- Log amount
- Encoded transaction types

### 3️⃣ Handling Class Imbalance
Fraud cases are extremely rare (<1%), so:
- Used class weighting during training

### 4️⃣ Model Building
Used **Random Forest Classifier** because:
- Handles nonlinear relationships
- Works well on large datasets
- Robust to outliers
- Provides feature importance

### 5️⃣ Evaluation Metrics
- Precision
- Recall (priority)
- F1-score
- ROC-AUC
- Confusion Matrix

---

## 📈 Results

The model achieved:

- High Recall → catches most frauds
- Strong ROC-AUC score
- Interpretable predictions

Fraud detection prioritizes **recall**, because:
> Missing fraud costs money, false alarms only cause minor inconvenience.

---

## 🔍 Key Fraud Indicators (Insights)

Top features influencing fraud:

- Large transaction amounts
- Transfer & cash-out transactions
- Sudden balance drops
- Zero remaining balance
- Flagged high-value transfers

These patterns match real-world fraud behavior where attackers quickly empty accounts.

---

## 🧠 Business Recommendations

### Technical
- Real-time fraud scoring API
- OTP verification for large transfers
- 2FA authentication
- Transaction limits

### Analytical
- Risk scoring for customers
- Daily anomaly detection
- Fraud monitoring dashboards

### Operational
- Instant alerts
- Account freeze mechanism
- Blacklisting suspicious accounts

---

## 📊 How to Run

### Install dependencies
