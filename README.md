<div align="center">

# SyriaTel Customer Churn Prediction

<img src="https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Complete-00C851?style=for-the-badge"/>

**An end-to-end machine learning project predicting telecom customer churn using classification models — achieving AUC 0.898 with a tuned Random Forest.**

*Built by Vishvi · Data Science & AI Practitioner · IBM Professional Certificate (Coursera)*

</div>

---

## 📌 Business Problem

SyriaTel is experiencing significant revenue loss due to customer churn. Retaining an existing customer costs **5–7× less** than acquiring a new one. This project builds a predictive model to identify customers at high risk of churning — enabling the business to act *before* they leave.

> **Goal:** Build a binary classifier that accurately identifies churners, maximising **recall** to minimise missed at-risk customers.

---

## 📊 Dataset

| Attribute | Details |
|---|---|
| **Source** | [Kaggle — Churn in Telecom Dataset](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset) |
| **Rows** | 3,333 customers |
| **Features** | 20 (call usage, charges, plans, service calls) |
| **Target** | `churn` (True / False) — 14.5% positive class |
| **Class Imbalance** | Yes — handled via `class_weight='balanced'` |

---

## 🤖 Models Built

| Model | Accuracy | Recall | AUC |
|---|---|---|---|
| Logistic Regression (Baseline) | 0.86 | 0.54 | 0.82 |
| Decision Tree | 0.91 | 0.72 | 0.85 |
| Random Forest | 0.94 | 0.78 | 0.91 |
| **Tuned Random Forest ✅** | **0.95** | **0.80** | **0.898** |

---

## 🔑 Top Churn Predictors

1. **Total day minutes** — High usage = higher bill = higher churn risk
2. **Customer service calls** — Frequent complaints signal dissatisfaction
3. **International plan** — International plan holders churn at higher rates
4. **Total evening minutes** — Secondary usage driver
5. **Voice mail plan** — Customers without voicemail churn more

---

## 💡 Business Recommendations

| Finding | Recommendation |
|---|---|
| High-usage customers churn more | Introduce loyalty discounts for top-tier usage bands |
| 3+ service calls = high churn risk | Trigger proactive outreach after the 2nd service call |
| International plan users churn | Review international pricing vs. competitors |

---

## 👩‍💻 About the Author

**Vishvi** — Data Science & AI Practitioner, transitioning from English Literature (BA Hons, University of Delhi). Currently completing the **IBM Data Science Professional Certificate** on Coursera.

> *"My background in literature sharpens how I tell the story behind the data."*

[![GitHub](https://img.shields.io/badge/GitHub-vivi-181717?style=flat&logo=github)](https://github.com/vivi)
