# AML Guard: Detecting Suspicious Financial Transactions

Built from scratch using synthetic data and machine learning.

## Project Overview

AML Guard is an end-to-end Anti-Money Laundering (AML) system that simulates real-world financial transaction patterns, detects suspicious activity, and explains fraud predictions — all using a dataset created from scratch.

Since real AML data is confidential, this project builds a realistic synthetic dataset and uses both rule-based logic and machine learning to flag suspicious behavior.

## Objectives

- Simulate realistic financial transaction behavior, including known laundering tactics
- Detect suspicious transactions using both business rules and ML
- Visualize fraud patterns across users, time, and countries
- Explain why a transaction was flagged as suspicious

## Project Workflow

### 1. Synthetic Data Creation

Created a fake but realistic dataset:
- 20,000+ transactions
- Customers, senders, receivers, timestamps
- Countries including high-risk locations
- Transaction types (transfer, deposit, payment, etc.)
- Risk score + binary label `is_suspicious`

This step replaces public datasets and demonstrates understanding of how fraud occurs.

### 2. Exploratory Data Analysis (EDA)

Explored patterns in the data:
- Who sends the most money
- Country-wise transaction heatmaps
- Suspicious vs normal behavior
- Time-of-day patterns

This informed both rule design and feature creation.

### 3. Rule-Based Detection

Implemented basic detection logic:
- Large amounts to offshore accounts
- Too many transactions in a short time
- Round-number transactions (e.g., 1000000)
- Unusual country patterns

This was used to flag initial suspicious activity for model training and comparison.

### 4. Feature Engineering

Created features from behavior:
- Rolling averages per user
- Std deviation of amounts
- Time gaps between transactions
- % offshore transactions
- Unique countries interacted with

These were used to improve model performance and represent transaction behavior clearly.

### 5. Machine Learning Detection

Models used:
- Isolation Forest (unsupervised)
- XGBoost or similar tree-based model (semi-supervised)

ML models were trained on rule-labeled data or used to detect anomalies.

### 6. Model Evaluation

Key metrics used:
- Precision
- Recall
- F1 Score
- Confusion matrix

Focused on reducing false positives while catching true fraud.

### 7. Explainability

Used feature importance and/or SHAP to:
- Understand what factors led to a prediction
- Provide transparency in suspicious flags

### 8. Visualization / Reporting

Visual outputs included:
- Suspicious activity by country
- High-risk users
- Transaction trends over time

Optional: built a lightweight Streamlit dashboard for interactivity.

## Tools Used

| Area             | Tools / Libraries             |
|------------------|-------------------------------|
| Data Creation    | Python, NumPy, pandas         |
| EDA              | pandas, matplotlib, seaborn   |
| Rule Logic       | Custom Python rules           |
| ML Models        | scikit-learn, XGBoost         |
| Metrics          | sklearn.metrics               |
| Dashboard (opt)  | Streamlit                     |
| Documentation    | Markdown, Visuals             |


## What This Project Demonstrates

- Practical understanding of fraud patterns and AML systems
- Ability to generate realistic data from scratch
- Full data science lifecycle: from raw data to modeling and explanation
- Balanced approach using both logic and machine learning
- Clean separation of concerns across repo

## Possible Next Steps

- Add graph-based sender-receiver fraud detection
- Introduce autoencoder-based deep learning anomaly detection
- Create a feedback loop for active learning and retraining
- Deploy live demo and allow CSV upload + alerts
