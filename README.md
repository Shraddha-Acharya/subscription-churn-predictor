# 🔄 Subscription Fatigue (Churn) Predictor

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Scikit-Learn](https://img.shields.io/badge/ScikitLearn-ML-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

## 📌 Overview
An end-to-end machine learning project that predicts which customers
are likely to cancel their subscriptions. Built as a "warning system"
for subscription businesses (like Netflix or Spotify) to proactively
retain at-risk customers before they leave.

## 🎯 Results
| Metric | Score |
|--------|-------|
| ROC-AUC | **0.84** |
| Recall (Churners) | **71%** |
| Accuracy | **76%** |
| Churners Caught | **264 / 374** |

## 💡 Key Insights Discovered
- **26.5%** overall churn rate — 1 in 4 customers leaves
- Month-to-month customers churn at **42.7%** vs **2.8%** for two-year contracts
- Churned customers pay **$13 more per month** on average
- **52.9%** of new customers (≤6 months) churn vs 19.5% of established ones
- Fiber optic customers churn at **41.9%** vs 7.4% for no internet

## ⚙️ Custom Feature Engineering
Created 4 new features from scratch — the most impactful being:
- **ValueScore** = MonthlyCharges / (tenure+1) → became the **#1 most
  predictive feature** out of 34 total, outperforming all original columns
- **IsNewCustomer** → tenure ≤ 6 months, churn rate 52.9%
- **IsSeniorOnFiber** → highest risk group at 47.3% churn
- **ChargesPerMonth** → lifetime spending pattern

## 🛠️ Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn
- **Model:** Random Forest Classifier
- **Platform:** Google Colab
- **Dataset:** [Telco Customer Churn - Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## 📁 Files
| File | Description |
|------|-------------|
| `churn_predictor.ipynb` | Main notebook with full analysis |
| `WA_Fn-UseC_-Telco-Customer-Churn.csv` | Dataset |

## 🚀 How to Run
1. Open `churn_predictor.ipynb` in Google Colab
2. Upload `WA_Fn-UseC_-Telco-Customer-Churn.csv` when prompted
3. Run all cells in order

## 📊 Project Workflow
1. **Data Loading & Cleaning** — Fixed data types, handled missing values
2. **EDA** — Discovered 5 key churn patterns through visualization
3. **Feature Engineering** — Created 4 custom features
4. **Model Building** — Random Forest with class balancing
5. **Evaluation** — ROC-AUC 0.84, confusion matrix, feature importance
