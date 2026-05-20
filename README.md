# 🏦 Bank Customer Churn Prediction

> **Predicting which bank customers are likely to leave — and helping the bank stop them in time.**

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Plots-4C72B0)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Project Overview

Customer churn is one of the **biggest revenue problems** for banks. Acquiring a new customer costs **5x more** than retaining an existing one — yet most banks discover their customers have left only **after** they're gone.

This project builds an end-to-end machine learning system that identifies customers most likely to leave a European bank, enabling **proactive retention** instead of reactive damage control.

### 🎯 Problem Statement

> *"Can we predict which customers will leave the bank in the next quarter — so we can take action before they actually leave?"*

---

## 💼 Business Impact

| Metric | Value |
|---|---|
| **Churners identified per 100 actual churners** | 65 |
| **High-risk customers flagged in test set** | 214 |
| **Estimated annual savings (30% retention)** | ~₹3 crore |
| **Model ROC-AUC** | 0.86 |

If the bank uses this model to target the top 20% highest-risk customers each month, **retaining even 30% of them** can save crores in lost customer lifetime value.

---

## 🗂️ Dataset

**Source:** European Bank Customer Records (10,000 customers)

| Feature | Description |
|---|---|
| `CreditScore` | Customer's credit score |
| `Geography` | Country (France / Spain / Germany) |
| `Gender` | Male / Female |
| `Age` | Customer's age |
| `Tenure` | Years as a customer |
| `Balance` | Current bank balance |
| `NumOfProducts` | Number of bank products held |
| `HasCrCard` | Has credit card (0/1) |
| `IsActiveMember` | Active member status (0/1) |
| `EstimatedSalary` | Estimated annual salary |
| **`Exited`** | **Target — 1 if customer left, 0 if stayed** |

---

## 🛠️ Tech Stack

- **Language:** Python 3.10
- **Data Manipulation:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Machine Learning:** scikit-learn (Random Forest Classifier)
- **Statistical Analysis:** scipy (Z-score for outlier removal)
- **Environment:** Jupyter Notebook / Google Colab

---

## 📋 Project Workflow

```
1. Import Libraries
2. Load Dataset
3. Understand Dataset (shape, info, describe)
4. Data Cleaning (drop unnecessary columns)
5. Check Target Distribution
6. Business Insights from Data (5 data-backed findings)
7. Encode Categorical Variables (Label + One-Hot)
8. Feature Engineering (4 new features)
9. Correlation Heatmap
10. Outlier Removal (Z-Score)
11. Define Features (X) and Target (y)
12. Feature Scaling (StandardScaler)
13. Train / Test Split (stratified)
14. Build Random Forest Model
15. Predictions
16. Model Evaluation (Accuracy, Precision, Recall, ROC-AUC)
17. Feature Importance Analysis
18. Actual vs Predicted Comparison
19. Business Recommendations
```

---

## 🔍 Key Business Insights

Five data-driven findings from the analysis:

1. **🌍 Germany has 2× higher churn rate (32%)** than France or Spain (16%)
2. **👤 Female customers churn 50% more than male customers** (25% vs 16%)
3. **🛒 Customers with 3+ products churn 83% of the time** — possible upsell or fee issue
4. **⚡ Inactive members churn at double the rate** of active ones (27% vs 14%)
5. **📊 Customers aged 50–60 have the highest churn rate (56%)** — likely retirement-driven

These insights alone — without any model — can guide retention strategy.

---

## 🤖 Model Performance

**Algorithm:** Random Forest Classifier
**Configuration:** `n_estimators=300, max_depth=10, class_weight='balanced'`

| Metric | Score |
|---|---|
| **Accuracy** | 84.4% |
| **ROC-AUC** | 0.86 |
| **Precision (Churned)** | 0.61 |
| **Recall (Churned)** | 0.65 |
| **F1-Score (Churned)** | 0.63 |

> **Why `class_weight='balanced'`?** The dataset has 80% non-churners and 20% churners. Without balancing, the model would get ~80% accuracy by just predicting "no churn" for everyone — useless. Class balancing boosted recall from 46% → 65%, meaning the model now catches the customers we actually care about.

### Top 5 Features Driving Churn

| Rank | Feature | Importance |
|---|---|---|
| 1 | Age | 27% |
| 2 | NumOfProducts | 14% |
| 3 | EngagementProduct | 8% |
| 4 | Balance | 8% |
| 5 | AgeTenure | 7% |

---

## 💡 Business Recommendations

Based on the analysis, here are actionable steps the bank can take:

### 🎯 Immediate Actions
1. **Launch a "Germany Loyalty Program"** — target the country with highest churn
2. **Re-engage inactive members** via personalized emails & app notifications
3. **Audit the 3+ product strategy** — investigate why over-bundling backfires
4. **Senior citizen retention plan** — assisted banking, premium FDs for 50+ customers
5. **Gender-specific engagement campaigns** to address higher female churn

### 📊 Operational Plan
- Run the model on the **current customer base monthly**
- Sort customers by `Churn_Probability`
- Focus retention efforts on the **top 20% highest-risk customers** for best ROI

---

## 📁 Repository Structure

```
bank-churn-prediction/
│
├── Bank_Churn_Prediction_Professional.ipynb   # Main notebook
├── European_Bank.csv                          # Dataset
├── README.md                                  # You are here
└── requirements.txt                           # Dependencies
```

---

## 🚀 How to Run

### Option 1: Google Colab (Recommended for Beginners)
1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload `European_Bank.csv` to the Colab session
3. Run all cells

### Option 2: Local Jupyter
```bash
# Clone the repo
git clone https://github.com/VaibhavZagade/Bank_Customer_Churn_Prediction.git
cd bank-churn-prediction

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook Bank_Churn_Prediction_Professional.ipynb
```

### `requirements.txt`
```
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
jupyter
```

---

## 📸 Sample Outputs

### Churn Distribution
20% of customers churned — imbalanced dataset handled with `class_weight='balanced'`.

### Confusion Matrix
Shows true positives, true negatives, false positives, and false negatives at a glance.

### Feature Importance
Age and Number of Products dominate the prediction.

*(See the notebook for full visualizations.)*

---

## 🎓 Skills Demonstrated

- ✅ **Data Preprocessing** — handling categorical variables, encoding, scaling
- ✅ **Feature Engineering** — creating 4 derived features that boost model performance
- ✅ **Exploratory Data Analysis (EDA)** — visualizations and statistical insights
- ✅ **Outlier Detection** — Z-Score method
- ✅ **Machine Learning** — Random Forest with class balancing
- ✅ **Model Evaluation** — Accuracy, Precision, Recall, F1, ROC-AUC, Confusion Matrix
- ✅ **Business Storytelling** — translating model output into business actions

---

## 🔮 Future Improvements

- [ ] Try **XGBoost / LightGBM** for potentially better performance
- [ ] **Hyperparameter tuning** with GridSearchCV
- [ ] Apply **SMOTE** for advanced class balancing
- [ ] Build a **Power BI dashboard** for the bank's retention team
- [ ] Deploy as a **Flask / Streamlit web app**
- [ ] Set up **monthly batch predictions** with scheduled scoring

---

## 👤 Author

**Vaibhav Zagade**
*Data Analyst | Python | SQL | Power BI | Machine Learning*

📍 Pune, Maharashtra, India

🔗 **Connect with me:**
- LinkedIn: www.linkedin.com/in/vaibhav-zagade-b03328404
- GitHub: https://github.com/VaibhavZagade
- Email: zagadevaibhav39@gmail.com

---

## 🙏 Acknowledgments

- Dataset originally based on the **Churn Modelling** dataset format (publicly available)
- Inspired by real-world banking analytics use cases
- Thanks to mentors and the data science community for continuous learning resources

---

⭐ **If you found this project useful, please give it a star!** ⭐
