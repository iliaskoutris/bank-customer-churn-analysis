# Bank Customer Churn Analysis  
End-to-end Data Analytics & Machine Learning pipeline for predicting customer churn in a retail bank.

---

## Project Overview
This project builds a complete workflow to analyze, understand, and predict customer churn using machine learning.  
It includes data preprocessing, exploratory data analysis, statistical feature evaluation, feature engineering, modeling, and business insights.

The goal is not only to build a predictive model, but to understand **why customers leave** and provide actionable recommendations for retention strategies.

---

---

## 📊 Methodology

### **1. Data Preparation**
- Cleaning missing values  
- Data type corrections  
- Removing duplicates  
- Outlier detection (IQR method)  
- Validation of variable ranges  
- Exporting clean dataset to `data/processed/`

---

### **2. Exploratory Data Analysis (EDA)**
- Univariate & bivariate distributions  
- Churn distribution across countries, age, tenure, products, activity  
- Heatmaps, boxplots, countplots  
- Identification of high-risk segments

---

### **3. Statistical Analysis**
- Welch’s t-tests + FDR correction  
- Chi-square tests + Cramér’s V for categorical variables  
- Mutual Information ranking  
- Effect sizes (Cohen’s d)  
- Interpretation of statistically significant drivers of churn

---

### **4. Feature Engineering**
- Age & tenure buckets  
- Activity status  
- Product categories  
- High-value / low-value customer flags  
- Interaction features (e.g., `inactive × high_balance`)  
- Customer segments combining Value × Activity × Age

---

### **5. Modeling**
Model used: **Logistic Regression**

Steps:
- Train-test split  
- Standard scaling  
- `class_weight="balanced"` to handle imbalance  
- ROC AUC & Precision-Recall evaluation  
- Threshold tuning (0.45 chosen for higher recall)  
- Odds ratios for interpretability  

---

## 📈 Model Performance

| Metric | Score |
|--------|--------|
| **ROC AUC** | ~0.82–0.85 |
| **Precision @ Threshold 0.45** | High, depending on class weight |
| **Recall @ Threshold 0.45** | Significantly improved for churners |
| **Top Features** | Age, Activity, Number of Products, Balance, Segment |

---

## Business Insights

The model and statistical analysis highlight that churn is strongly associated with:

- **Inactive customers with high balances**  
- **Customers with 3+ products**  
- **Ages between 45–60**  
- **High-value customers who recently reduced activity**  
- **Certain geographic segments (e.g., Germany)**
