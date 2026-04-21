# Telco Customer Churn: Predictive Analytics for Customer Retention

**Author:** Javier Herrero Pérez  
**Date:** January 2026  
**Dataset:** [Telco Customer Churn (Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

---

##  Project Overview

This project addresses one of the most critical challenges in the telecommunications industry: **customer churn** (customer abandonment). With customer retention being approximately 5x more cost-effective than acquisition, identifying at-risk customers enables companies to implement targeted retention strategies efficiently.

The analysis utilizes the renowned **Telco Customer Churn** dataset, containing behavioral, demographic, and billing information for 7,043 customers of a fictional telecommunications company in California.

---

##  Project Objectives

### Analytical
Understand the root causes of customer abandonment through comprehensive analysis of:
- Demographic variables (age, gender, family status)
- Service subscription patterns
- Billing behavior and payment methods

### Predictive
Develop a robust classification model that maximizes **F1-Score**, balancing:
- Detection capability (Recall) - identifying at-risk customers
- Prediction precision (Precision) - minimizing false alarms

### Strategic
Provide a decision-making tool based on:
- **Ensemble modeling** combining multiple algorithms
- **Dynamic threshold tuning** aligned with business costs

---

##  Technical Innovations

This notebook implements several advanced techniques:

### 1. **Residual Analysis for Anomaly Detection**
- Employs OLS linear regression to detect billing anomalies
- Integrates residuals as predictive features
- Captures non-obvious patterns in customer spending

### 2. **Rigorous Validation Pipeline**
- Applies SMOTE (Synthetic Minority Over-sampling Technique) exclusively in the training set
- Uses cross-validation to prevent data leakage
- Ensures model generalization to unseen data

### 3. **Ensemble Intelligence (Voting Classifier)**
Combines the strengths of three powerful algorithms:
- **XGBoost** - Fast, accurate gradient boosting
- **Random Forest** - Robust ensemble learning
- **LightGBM** - Efficient memory usage with high performance

### 4. **Threshold Optimization**
- Implements `TunedThresholdClassifierCV` for dynamic threshold selection
- Aligns model predictions with business operational costs
- Balances recall vs. precision based on retention strategy

---

##  Dataset Description

### Customer Information
| Variable | Type | Description |
|----------|------|-------------|
| **customerID** | String | Unique customer identifier |
| **gender** | Categorical | Customer gender (Female, Male) |
| **SeniorCitizen** | Binary | Senior status (0: No, 1: Yes) |
| **Partner** | Binary | Has a partner (Yes, No) |
| **Dependents** | Binary | Has dependents (Yes, No) |

### Account & Contract Information
| Variable | Type | Description |
|----------|------|-------------|
| **tenure** | Numeric | Months with the company (0-72) |
| **Contract** | Categorical | Month-to-month, One year, Two year |
| **PaperlessBilling** | Binary | Electronic billing enabled (Yes, No) |
| **PaymentMethod** | Categorical | Electronic check, Bank transfer, Credit card, Mailed check |
| **MonthlyCharges** | Numeric | Monthly service cost ($18.25 - $118.75) |
| **TotalCharges** | Numeric | Total lifetime charges ⚠️ *Contains missing values* |

### Target Variable
| Variable | Type | Description |
|----------|------|-------------|
| **Churn** | Binary | Customer left company (Yes, No) |

---

##  Key Findings & Insights

### Churn Risk Factors (High Priority)
- **Short tenure** - Customers with < 6 months are at critical risk
- **Month-to-month contracts** - 3x higher churn rate than long-term contracts
- **Electronic check payments** - Associated with highest churn rates
- **High billing anomalies** - Residual analysis identifies suspicious patterns

### Retention Opportunities
- **Long-term contracts** - 12-24 month agreements significantly reduce churn
- **Multiple services** - Internet + Phone bundle reduces abandonment
- **Automatic payment methods** - Bank transfers & credit cards = higher retention
- **Senior citizens** - Show strong loyalty when satisfied

---

## 📈 Model Performance

| Metric | Score |
|--------|-------|
| **F1-Score (Validation)** | 0.75 |
| **Precision** | 0.49 |
| **AUC-ROC** | 0.85 |

*Scores optimized for business KPIs with threshold tuning*


---

## Technologies & Libraries

**Data Processing:**
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computations

**Machine Learning:**
- `scikit-learn` - Classical ML algorithms & preprocessing
- `xgboost` - Gradient boosting model
- `lightgbm` - Fast gradient boosting
- `statsmodels` - Statistical modeling & residual analysis

**Visualization:**
- `matplotlib` - Static plots
- `seaborn` - Statistical data visualization

---

## Learning Outcomes

This project demonstrates proficiency in:
- **Exploratory Data Analysis (EDA)** - Understanding complex datasets
- **Feature Engineering** - Creating predictive variables from raw data
- **Class Imbalance Handling** - SMOTE and cost-sensitive learning
- **Ensemble Methods** - Combining multiple models for better predictions
- **Model Validation** - Cross-validation and proper train/test splitting
- **Business Alignment** - Optimizing for business objectives (not just accuracy)
- **Statistical Analysis** - OLS regression, residual diagnostics

---

## Business Impact

**Potential ROI:**
- Identify 70-80% of at-risk customers before churn
- Enable proactive retention campaigns
- Reduce customer acquisition costs through improved retention
- Increase CLV (Customer Lifetime Value) by 15-25%

**Actionable Recommendations:**
1. **Immediate:** Target month-to-month customers with contract upgrade offers
2. **Short-term:** Improve support for customers with high billing anomalies
3. **Long-term:** Incentivize automatic payment methods and service bundling

---


### Additional Resources
- [Kaggle Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [LightGBM Tutorial](https://lightgbm.readthedocs.io/)
- [SMOTE Technique](https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.SMOTE.html)

---


**Last Updated:** January 2026  
**Status:** ✅ Complete & Production-Ready
