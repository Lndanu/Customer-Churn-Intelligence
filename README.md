# Customer-Churn-Intelligence
This project sets out to harness machine learning to predict which telecom customers might leave, using real-world industry data. By exploring different models, we hope to uncover the most important reasons behind customer churn. Ultimately, the goal is to equip businesses with practical, data-backed strategies for keeping customers longer.

# Business Objective
For telecom providers, losing customers hurts the bottom line. Early predictions make it possible to reach out and win back at-risk users before it’s too late. My work goes beyond simple predictions—it classifies customers by churn risk, highlights the strongest drivers of that risk, and delivers clear, actionable recommendations to help companies craft more effective retention plans.

## Overview
This project aims to predict customer churn in a telecommunications company using machine learning classification models. The goal is to identify patterns that indicate which customers are likely to stop using the service, allowing the business to take proactive retention measures.


## Business and Data Understanding

### Business Context
Telecom companies often face significant losses due to customer churn. By identifying at-risk customers early, the company can deploy retention strategies such as personalized offers or targeted communications.

### Stakeholder
The primary stakeholder is the **Customer Retention Team** at a telecommunications provider. This team is responsible for reducing churn rates and increasing customer lifetime value.

### Problem Statement
"Can we predict whether a customer will churn based on their demographic and usage behavior?"

### Objective
To build a classification model that predicts customer churn and provides actionable insights to help reduce it.

---

## Dataset Description

- Source: [BigML / Telco Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn)
- Rows: ~3,300
- Features: 20
- Target: `Churn` (Yes/No)
- Feature categories:
  - **Demographics** (e.g., gender, senior citizen)
  - **Account Info** (e.g., contract type, tenure)
  - **Services** (e.g., internet, phone lines)
  - **Billing Info** (e.g., payment method, monthly charges)

---

##  Modeling Process

### Preprocessing
- Handled missing values in `TotalCharges`
- Converted categorical variables using One-Hot Encoding
- Scaled numerical features (`MonthlyCharges`, `tenure`, etc.)
- Split dataset into **80% training** and **20% test** sets

### Baseline Model
- **Logistic Regression**
  - Simple, interpretable model
  - Trained on scaled data
  - Used as a benchmark for evaluating more complex models

### Improved Models
1. **Random Forest Classifier**
   - Handles non-linearity
   - Reduced overfitting with `max_depth` tuning
   - Feature importance extracted

2. **XGBoost Classifier**
   - Boosted trees for higher accuracy
   - Tuned `learning_rate`, `n_estimators`, and `max_depth`

---

## Evaluation

| Model               | Accuracy | Precision | Recall | F1 Score |
|--------------------|----------|-----------|--------|----------|
| Logistic Regression| 0.80     | 0.72      | 0.65   | 0.68     |
| Random Forest       | 0.84     | 0.76      | 0.70   | 0.73     |
| XGBoost             | 0.86     | 0.78      | 0.72   | 0.75     |

> Chosen Metric: **Recall**, since it's more costly to miss a churner than to wrongly flag a loyal customer.

---

## Key Findings

### Feature Importance (Top 5)
- **Contract Type**: Month-to-month contracts had the highest churn rate.
- **Tenure**: New customers churn more often.
- **Paperless Billing**: Customers with paperless billing are more likely to churn.
- **Monthly Charges**: Higher charges are linked to higher churn.
- **Tech Support**: Those without tech support services churn more frequently.

---

## Recommendations

1. **Incentivize long-term contracts** to reduce churn probability.
2. **Target high monthly charge users** with discount bundles or loyalty rewards.
3. **Follow up on new customers** early in their lifecycle to improve onboarding.
4. **Offer value-added services** like tech support to increase stickiness.

---

## Limitations
- Historical data may not capture future behavioral shifts.
- Some features may be correlated (e.g., services offered as part of a bundle).
- Class imbalance (churned vs. non-churned) may affect model generalization.

---


## Conclusion

This classification model successfully identifies customers at risk of churning and provides actionable insights for the customer retention team. With further refinement and live deployment, this tool can be integrated into CRM systems to trigger timely interventions and retain high-value customers.

---

## Links

- Linkedn: https://www.linkedin.com/in/luciana-ndanu-24a71bb6/
- Email: lucianandanu@gmail.com






