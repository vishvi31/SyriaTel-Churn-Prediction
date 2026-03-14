Here's your complete copy-paste ready README with everything included:

---

# 📱 SyriaTel Customer Churn Prediction

## **An End-to-End Machine Learning Project**

https://github.com/vishvi31/SyriaTel-Churn-Prediction/blob/ba9bf1cb974409adf97985f2bc55a3fe1a1377da/SyriaTel%20Customer%20Churn%20Prediction%20Dashboard.png?raw=true

---

## **📌 Project Overview**

SyriaTel, a telecommunications company, is losing customers every month. This project builds a **Machine Learning system** that predicts **which customers are likely to cancel their service** — so SyriaTel can take action before they leave.

This is a complete Data Science project covering data exploration, preprocessing, feature engineering, model building, hyperparameter tuning, and business recommendations.

---

## **❓ Business Questions This Project Answers**

1. What is the current churn rate at SyriaTel?
2. Which customers are most likely to churn?
3. Does having an international plan increase churn risk?
4. How do customer service calls relate to churn?
5. Are high-spending customers more likely to leave?
6. Which features are the strongest predictors of churn?
7. Which Machine Learning model predicts churn most accurately?

---

## **📊 Dataset Information**

| Detail | Value |
|---|---|
| **Source** | [Kaggle — Churn in Telecoms Dataset](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset) |
| **Company** | SyriaTel (real telecom company) |
| **Total Customers** | 3,333 |
| **Total Features** | 21 |
| **Target Column** | `churn` (True = churned, False = stayed) |
| **Churn Rate** | 14.49% |
| **Missing Values** | None |

---

## **📁 Project Structure**

```
syriatel-churn-prediction/
│
├── SyriaTel_Churn_Prediction.ipynb           ← Full project code
├── SyriaTel_Customer_Churn_Dashboard.png     ← Final dashboard
└── README.md                                 ← Project documentation
```

---

## **⚙️ Project Pipeline**

```
Phase 1 → Import Libraries
Phase 2 → Load Dataset (via URL, no download needed)
Phase 3 → Exploratory Data Analysis (EDA)
Phase 4 → Data Preprocessing & Feature Engineering
Phase 5 → Train-Test Split & Feature Scaling
Phase 6 → Model Building & Evaluation
Phase 7 → Hyperparameter Tuning (GridSearchCV)
Phase 8 → Feature Importance & Business Insights
```

---

## **🛠️ Tech Stack**

| Tool | Purpose |
|---|---|
| **Python 3** | Programming language |
| **Google Colab** | Development environment |
| **pandas & numpy** | Data manipulation |
| **matplotlib & seaborn** | Visualization |
| **scikit-learn** | ML models & evaluation |

---

## **📈 Dashboard Explained**

### **🔢 KPI Cards — The Big Numbers**

> **Total Customers: 3,333 | Churned: 483 | Retained: 2,850**

- SyriaTel is losing **483 customers** — that's real money walking out the door
- At an average bill of $60/month → **$28,980 lost every single month**
- Multiply by 12 → **$347,760 lost per year** just from churn

---

### **🥧 Overall Churn Distribution**

> **85.5% Stayed | 14.5% Churned**

- The dataset is **imbalanced** — only 14.5% churned
- This is why we used `class_weight='balanced'` in all models
- Using plain accuracy here would be misleading — a model that always says "stayed" would get 85.5% accuracy but catch **zero churners!**

---

### **🌍 International Plan vs Churn %**

> **Customers WITH international plan churn at ~42% — 4x higher than average!**

- Customers WITHOUT international plan → churn rate ~10%
- Customers WITH international plan → churn rate ~42%
- **This is the single most alarming finding in the entire project**
- Customers are likely signing up, getting a huge unexpected bill, and immediately cancelling

**💼 Business Action:** Redesign international plan pricing. Offer flat-rate international bundles. Call international plan holders proactively after first bill.

---

### **📬 Voicemail Plan vs Churn %**

> **Voicemail plan holders churn significantly LESS**

- Customers WITHOUT voicemail → higher churn
- Customers WITH voicemail → much lower churn
- Voicemail acts as a **"loyalty anchor"** — more services = more attached to the network

**💼 Business Action:** Bundle voicemail for free with other plans as a retention strategy.

---

### **📞 Customer Service Calls vs Churn — DANGER ZONE**

> **4+ customer service calls = customer is about to leave!**

- 0 to 3 calls → mostly green (stayed customers)
- 4+ calls → mostly pink (churned customers)
- The **yellow dotted line at 4 calls** marks the danger zone
- Every extra call beyond 3 is a **red alert signal**

**💼 Business Action:** Build an automated alert — when a customer makes their **3rd service call**, immediately assign a retention specialist to contact them with a special offer before they make that 4th call.

---

### **⏱️ Total Day Minutes vs Churn**

> **Heavy users (200+ minutes/day) show more churn in the pink distribution**

- Both churned and stayed customers use a wide range of minutes
- But the overlap at high usage shows heavy users are at risk
- Heavy usage = big monthly bill = higher chance of switching to a competitor

**💼 Business Action:** Offer unlimited day plans or loyalty discounts specifically targeting customers using 200+ minutes per day.

---

### **🔝 Top 10 Feature Importances**

> **Top 5 drivers of churn prediction:**

| Rank | Feature | Why It Matters |
|---|---|---|
| **1** | total_spend | Overall money paid — bill shock drives churn |
| **2** | customer service calls | Frustration indicator — strongest behavioral signal |
| **3** | international plan | High-risk segment identified |
| **4** | total day charge | Direct billing pressure |
| **5** | total day minutes | Usage volume linked to cost |

- Features highlighted in **cyan** are above average importance
- The model learned that **money + frustration = churn** — exactly what human logic would tell us too!

---

### **📈 ROC Curve — All Models**

> **Tuned Random Forest achieved the best AUC of 0.898**

| Model | AUC Score |
|---|---|
| Logistic Regression | 0.815 |
| Decision Tree | 0.870 |
| Random Forest | 0.898 |
| **Tuned Random Forest ⭐** | **0.898** |

- AUC of **0.898 means the model correctly ranks a churner above a non-churner 89.8% of the time**
- The closer the curve hugs the **top-left corner**, the better the model
- Tuned RF and RF curves are nearly identical — meaning our base RF was already very strong

---

### **📊 Model Comparison — Recall vs AUC**

> **Why Recall matters more than Accuracy for this problem:**

| Model | Recall | AUC |
|---|---|---|
| Logistic Regression | 0.74 | 0.81 |
| Decision Tree | 0.78 | 0.87 |
| Random Forest | 0.74 | 0.90 |
| **Tuned Random Forest ⭐** | **0.76** | **0.90** |

- **Missing a churner (False Negative)** = customer leaves = revenue lost forever ❌
- **False alarm (False Positive)** = we offer an unnecessary discount = small cost ✅
- Therefore **Recall is our most important metric** — we want to catch as many churners as possible

---

### **💰 Total Spend vs Churn (Boxplot)**

> **Churned customers were actually paying MORE than retained ones!**

- **Stayed customers** → median spend ~$55
- **Churned customers** → median spend ~$65, with outliers above $80
- This is the most counterintuitive finding — **high-value customers are leaving!**
- This means SyriaTel is losing its best customers, not just casual ones

**💼 Business Action:** Identify all customers spending above $70/month and assign them VIP status with proactive loyalty rewards, priority support, and personal account managers.

---

## **🤖 Final Model: Tuned Random Forest**

```
Best Model    →  Tuned Random Forest
AUC Score     →  0.898
Recall Score  →  0.76
Meaning       →  Correctly identifies 76% of churners before they leave
               →  Ranks churner above non-churner 89.8% of the time
```

---

## **💡 Top 5 Business Recommendations**

**1. 🌍 Fix International Plan Pricing — URGENT**
> 42% churn rate in this segment is catastrophic. Introduce flat-rate international bundles immediately.

**2. 📞 Build a 3-Call Alert System**
> When a customer calls support for the 3rd time, automatically trigger a retention outreach with a special offer.

**3. 💰 VIP Program for High Spenders**
> Customers spending $70+/month are your most valuable AND most at-risk. Protect them with loyalty rewards.

**4. 📬 Bundle Voicemail as a Free Perk**
> Voicemail holders churn less. Use it as a free add-on to increase customer stickiness across all plans.

**5. ⏱️ Unlimited Plans for Heavy Users**
> Target customers using 200+ day minutes with special unlimited plans before they switch to a competitor.

---

## **👤 Author**

Vishvi
- 🔗 LinkedIn: https://https:/518046360/www.linkedin.com/in/ vishvi-vishvi-
- 💻 GitHub: https://github.com/vishvi31

---

## **📄 License**
This project is open source and available under the [MIT License](LICENSE).

---

*⭐ If you found this project helpful, please give it a star on GitHub!
