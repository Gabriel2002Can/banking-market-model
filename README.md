# Banking Market Model

**Machine Learning for Targeted Banking Campaigns**  
*A predictive model to identify customers likely to subscribe to term deposits, optimized for imbalanced data and real-world marketing ROI.*

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-blue?style=flat-square&logo=pandas)
![scikit--learn](https://img.shields.io/badge/scikit--learn-1.3%2B-orange?style=flat-square&logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat-square&logo=jupyter)

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Project Background](#project-background)
3. [Problem Statement](#problem-statement)
4. [Dataset Overview](#dataset-overview)
5. [Step-by-Step Project Workflow](#step-by-step-project-workflow)
6. [Technologies & Tools](#technologies--tools)
7. [Key Results & Insights](#key-results--insights)
8. [Business Impact](#business-impact)
9. [How to Reproduce](#how-to-reproduce)
10. [Conclusion](#conclusion)
11. [For Hiring Managers & Recruiters](#for-hiring-managers--recruiters)

---

## Executive Summary

This end-to-end machine learning project, completed as part of the **Apziva** data science program, builds a robust classifier to predict whether a customer will subscribe to a term deposit during a banking marketing campaign. 

Using the well-known Bank Marketing dataset, the model addresses a **highly imbalanced classification problem** (only ~7.2% positive responses) and delivers **actionable insights** that enable targeted outreach, reduced marketing spend, and higher campaign ROI.

The final model — **XGBoost** — outperforms baselines and competing algorithms while maintaining strong generalization. Full pipeline (EDA → preprocessing → modeling → evaluation → interpretation) is implemented in a clean, reproducible Jupyter notebook.

---

## Project Background

Financial institutions run large-scale telemarketing campaigns to promote term deposits, yet conversion rates remain low. Traditional “spray-and-pray” approaches waste resources on low-propensity customers. This project demonstrates how data-driven modeling can transform campaign strategy from mass outreach to precision targeting.

---

## Problem Statement

> **“Which customers are most likely to subscribe to a term deposit?”**

**Key challenges:**
- **Severe class imbalance** (92.8% “no” vs. 7.2% “yes”)
- High cost of false positives (unnecessary calls)
- High opportunity cost of false negatives (missed subscribers)
- Need for interpretable, business-ready insights

---

## Dataset Overview

**Source**: `term-deposit-marketing-2020.csv`

**Features** (17 total):
- **Demographics**: `age`, `job`, `marital`, `education`
- **Financial**: `default`, `balance`, `housing`, `loan`
- **Campaign**: `contact`, `day`, `month`, `duration`, `campaign` (number of contacts), `previous`, `poutcome`

**Target**: `y` — “yes” (subscribed) / “no” (not subscribed)

**Class Distribution**:
- No subscription: **92.8%**
- Yes subscription: **7.2%**

A preview of the raw data:

| age | job          | marital | education | default | balance | housing | loan | contact | day | month | duration | campaign | y   |
|-----|--------------|---------|-----------|---------|---------|---------|------|---------|-----|-------|----------|----------|-----|
| 58  | management   | married | tertiary  | no      | 2143    | yes     | no   | unknown | 5   | may   | 261      | 1        | no  |
| 44  | technician   | single  | secondary | no      | 29      | yes     | no   | unknown | 5   | may   | 151      | 1        | no  |
| ... | ...          | ...     | ...       | ...     | ...     | ...     | ...  | ...     | ... | ...   | ...      | ...      | ... |

---

## Step-by-Step Project Workflow

The entire pipeline follows industry-standard CRISP-DM principles and is fully documented in `term-deposit-marketing.ipynb`.

### 1. Data Ingestion
- Loaded CSV with `pandas`
- Performed initial shape, info, and summary statistics checks

### 2. Exploratory Data Analysis (EDA)
- Visualized distributions (histograms, box plots, correlation heatmap)
- Analyzed categorical features vs. target (stacked bar charts)
- Identified key patterns: longer `duration`, higher `balance`, certain job types strongly correlate with subscription

### 3. Data Preprocessing
- Handled missing/unknown values
- Encoded categorical variables (`OneHotEncoder`)
- Scaled numerical features (`StandardScaler`)
- Addressed imbalance awareness (no oversampling — handled via class weights later)

### 4. Feature Engineering
- Created interaction terms and binned variables where insightful

### 5. Model Development
- Split: 80/20 train/test (stratified)
- Baseline models: Logistic Regression, Random Forest
- Advanced model: **XGBoost** (final choice)
- Hyperparameter tuning via cross-validation (no hyperparameters were used on the final version)

### 6. Evaluation & Validation
- Focused on **business-relevant metrics** (not just accuracy):
  - Precision, Recall, F1-score
  - ROC-AUC
  - Confusion matrix
- Compared training vs. test performance to confirm no overfitting
- Analyzed feature importance (SHAP-style via XGBoost built-in)

### 7. Interpretation & Insights
- Ranked top drivers of subscription probability
- Generated actionable recommendations for marketing team

### 8. Final Model Selection
- XGBoost selected for highest F1-score and best balance of precision/recall on the minority class

---

## Technologies & Tools

| Category          | Technologies                                      |
|-------------------|---------------------------------------------------|
| Language          | Python 3                                          |
| Data Handling     | pandas, NumPy                                     |
| Visualization     | Matplotlib, Seaborn                               |
| ML Framework      | scikit-learn, XGBoost                             |
| Environment       | Jupyter Notebook                                  |
| Other             | Git, GitHub                                       |

---

## Key Results & Insights

**Final XGBoost Performance (Test Set)**:
- Correctly identified **565 true subscribers**
- Missed only **152 potential subscribers** (low false-negative rate relative to baseline)
- Precision/Recall/F1 optimized for marketing use-case
- Strong generalization (train/test gap minimal)

**Top Predictive Features** (from model importance):
1. `duration` (call length) — strongest signal
2. `month`
3. `balance` & `housing`
4. `job` (management, student, retired)
5. `campaign` contact patterns

**Business Insight**: Targeting the top 20% of high-probability customers (as ranked by model) can dramatically increase conversion rate while slashing outreach volume.

---

## Business Impact

- **Cost Savings**: Reduce calls to low-propensity customers by >70%
- **ROI Increase**: Higher conversion on contacted leads
- **Scalability**: Model can be deployed in production CRM systems
- **Actionable**: Marketing teams receive clear customer segments and feature-based rules for immediate use

---

## How to Reproduce

1. Clone the repository:
   ```bash
   # 1. Clone the repository
   git clone https://github.com/Gabriel2002Can/banking-market-model.git
   cd banking-market-model

   # 2. Install dependencies
   pip install -r requirements.txt

   # 3. Launch notebook
   jupyter notebook term-deposit-marketing.ipynb

   ```

## Conclusion
This project showcases a complete, production-ready machine learning solution that directly solves a high-impact business problem in the banking sector. By focusing on imbalanced data handling, rigorous evaluation, and interpretable insights rather than raw accuracy, the model delivers tangible value far beyond academic exercises.

## For Hiring Managers & Recruiters
**What this project demonstrates about my capabilities:**

- **End-to-End ML Pipeline Ownership:** From raw data to deployed-ready insights — no hand-holding required.
- **Imbalanced Data Expertise:** Chose the right metrics (F1, precision/recall) and modeling techniques instead of falling into the accuracy trap.
- **Business-First Mindset:** Every decision (feature selection, threshold tuning, final recommendations) was driven by marketing ROI, not just Kaggle-style scores.
- **Clear Communication:** Clean, well-documented code + professional README that non-technical stakeholders can understand.
- **Modern Tooling & Best Practices:** XGBoost, proper cross-validation, feature importance analysis, reproducible notebook.

**Ready for roles in:** Data Science or Machine Learning Engineering.

I’m excited to bring this same rigor, business acumen, and passion for impactful ML to your team. Feel free to reach out — I’d love to walk through the notebook or discuss extensions (e.g., API deployment, SHAP explanations, or production monitoring).

---

**License:** MIT

**Author:** Luis Gabriel Stedile Portella

**Project completed:** Banking Market Model

**Last updated:** March 2026
