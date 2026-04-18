# 📊 Credit Risk Modeling: From Score to Decision

This project implements an end-to-end credit risk modeling pipeline, focusing not only on predicting default, but on transforming model outputs into actionable credit decisions.

---

## 🎯 Objective

Traditional credit scoring focuses on estimating the probability of default (PD).

In this project, the goal goes further:

> How do we move from a predictive model to a real credit decision?

The final output is a decision framework:
- Approve
- Approve with adjustment
- Reject

---

## 🧠 Approach

### 1. Data-driven target definition

Instead of assuming a fixed target, multiple definitions of default were tested:

- FPD (First Payment Default)
- EVER15
- EVER30
- OVER60

The final target was selected based on:
- coverage
- stability over time
- predictive performance

---

### 2. Temporal validation (Out-of-Time)

The model was evaluated using time-based splits to ensure realistic performance and avoid data leakage.

---

### 3. Model comparison

Two modeling approaches were evaluated:

- Logistic Regression (interpretable baseline)
- LightGBM (non-linear model with hyperparameter tuning)

Evaluation metrics:
- AUC
- PR-AUC
- KS
- Brier Score

The final model was selected based on validation performance.

---

### 4. Credit policy design

Instead of using arbitrary thresholds (e.g., PD < 5%), the decision cutoffs were derived from validation data:

- relationship between predicted PD and observed default
- expected loss behavior

This results in a data-driven segmentation:
- Low risk → Approve
- Medium risk → Approve with adjustment
- High risk → Reject

---

### 5. Model interpretability

SHAP values were used to understand feature importance and validate model behavior.

---

## 📈 Results

- Robust performance under temporal validation
- Clear separation of risk segments
- Data-driven credit policy aligned with real-world decision-making

---

## 🛠️ Tech Stack

- Python
- Pandas / NumPy
- Scikit-learn
- LightGBM
- SHAP
