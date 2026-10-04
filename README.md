# 📊 Virexo ML Internship — Task 3: Model Comparison & Explainable Prediction

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-v1.2%2B-orange?logo=scikit-learn)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success)]()

---

## 📌 Executive Summary
This repository contains an end-to-end Machine Learning pipeline comparing two distinct classification algorithms (**Logistic Regression** vs. **Decision Tree Classifier**) on a customer churn dataset. The objective is to evaluate model performance, demonstrate data cleaning rigor, deliver visual insights, and provide an explainable prediction system for business stakeholders.

---

## 🛠️ Project Workflow & Key Deliverables

### 1. Data Validation & Preprocessing
* **Integrity Audits:** Conducted explicit missing value checks (`.isnull().sum()`) and duplicate checks (`.duplicated().sum()`), confirming **0 missing entries** and **0 duplicate rows**.
* **Feature Encoding:** Applied One-Hot Encoding (`pd.get_dummies`) for categorical predictors (`contract_type`).
* **Train/Test Split:** Implemented a reproducible 80/20 stratified split (`random_state=42`).

### 2. Exploratory Data Analysis (EDA)
* Visualized key behavioral drivers using Seaborn boxplots and bar plots.
* Evaluated high-impact metrics including `monthly_charges` and `support_tickets` relative to customer churn outcomes.

### 3. Quantitative Model Comparison

| Evaluation Metric | Logistic Regression | Decision Tree Classifier | Selected Model |
| :--- | :---: | :---: | :---: |
| **Accuracy Score** | **100.00%** | **83.33%** | — |
| **Precision (Churned)** | 1.00 | 0.86 | ✅ Decision Tree |
| **Recall (Churned)** | 1.00 | 0.80 | ✅ Decision Tree |
| **F1-Score (Churned)** | 1.00 | 0.83 | ✅ Decision Tree |
| **Interpretability** | Linear Weights | Decision Rules (If-Else) | ✅ Decision Tree |

---

## 🎯 Model Selection Justification ("Why I Selected This Model")
Although Logistic Regression achieved 100% test accuracy, **Decision Tree Classifier (83.33%)** was selected for long-term deployment due to:
1. **Business Interpretability:** Decision Trees generate transparent decision thresholds, allowing non-technical stakeholders to understand churn triggers.
2. **Non-Linear Rules:** Captures complex, multi-variable customer interactions (e.g., combined effects of high support tickets and monthly charges).
3. **Overfitting Mitigation:** Addresses potential synthetic dataset overfitting risks associated with perfect linear separability.

---

## ⚠️ Model Assumptions & Limitations
* **Synthetic Data Reliance:** Built on a synthetic dataset designed for experimental validation.
* **Production Scope:** Highly accurate test metrics on small sample sizes may indicate mild overfitting. The baseline pipeline requires validation on real production CRM streams before real-time API integration.

---

## 📂 Repository Structure
```text
├── Virexo_Task3_Model_Comparison.ipynb            # Google Colab / Jupyter Notebook (Full Pipeline)
├── Virexo_Task3_Model_Comparison_Muhammad_Musa.pdf # Final PDF Deliverable Report
└── README.md                                      # Documentation & Executive Summary
