# Customer Churn Analysis

## Project Overview

Customer churn is a major business challenge because losing customers can reduce recurring revenue, increase customer acquisition costs, and weaken long-term customer value.

This project analyzes customer, subscription, and support data to understand **why customers are churning, which characteristics are associated with churn, and which customers should receive retention attention.**

The analysis focuses on actionable business questions rather than unnecessary exploratory analysis.

---

## Business Problem

The business wants to understand:

- How widespread is customer churn?
- Which contract and subscription plans have the highest churn?
- Are churned customers showing different churn-risk scores?
- Is customer dissatisfaction associated with churn?
- How does customer lifetime value differ between churned and retained customers?
- Which subscription sources contribute most to observed churn?
- Which individual customers should be prioritized for retention?

---

## Project Objectives

The main objectives were to:

1. Measure the overall customer churn rate.
2. Identify important patterns associated with customer churn.
3. Examine the relationship between churn and customer satisfaction.
4. Compare customer lifetime value between churned and retained customers.
5. Identify customers showing strong signs of churn risk.
6. Translate the findings into practical customer-retention recommendations.

---

## Dataset

The analysis uses three related tables.

### Customer Data

Contains customer-level information including:

- Customer ID
- Name
- Country
- State
- Gender
- Date of Birth
- Interests
- Pincode

### Subscription Data

Contains subscription and customer-value information including:

- Customer ID
- Subscription start date
- Subscription type
- Renewal date
- Plan type
- Contract type
- Cancellation date
- Cancellation reason
- Monthly charges
- Customer lifetime value (CLTV)
- Churn score
- Churn status

### Support Data

Contains customer-support activity including:

- Customer ID
- Complaint date
- Escalation status
- CSAT score
- Comments

---

## Tools & Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Plotly**
- **Jupyter Notebook**
- **Microsoft Excel**
- **SQLite**

Plotly was used to create interactive visualizations that allow users to hover over charts and explore individual data points.

---

## Data Preparation

The data preparation process included:

- Inspecting dataset structure and data types
- Checking for missing values
- Checking for duplicate records
- Converting date fields into appropriate datetime formats
- Cleaning inconsistent category labels
- Creating the customer churn indicator
- Aggregating support activity at the customer level
- Combining subscription and support information for customer-level risk analysis

No duplicate records were identified in the three source tables.

---

# Key Findings

## 1. Overall Churn

The dataset contains **21 customers**.

- **6 customers churned**
- **15 customers stayed**
- **Observed churn rate: 28.6%**

This means more than one-quarter of the observed customer base had churned.

---

## 2. Monthly Contracts Show Significantly Higher Churn

| Contract Type | Customers | Churned | Churn Rate |
|---|---:|---:|---:|
| Annual | 12 | 1 | 8.3% |
| Monthly | 9 | 5 | 55.6% |

Monthly-contract customers had a substantially higher observed churn rate than annual-contract customers.

This makes monthly customers an important retention segment for the business to investigate.

---

## 3. Basic Plan Has the Highest Churn Rate

| Plan | Customers | Churned | Churn Rate |
|---|---:|---:|---:|
| Basic | 5 | 3 | 60.0% |
| Standard | 9 | 2 | 22.2% |
| Premium | 7 | 1 | 14.3% |

The Basic plan recorded the highest observed churn rate.

The business should investigate whether pricing, features, perceived value, or customer experience may be contributing to this pattern.

---

## 4. Churn Scores Clearly Separate Churned Customers

| Customer Status | Average Churn Score | Median |
|---|---:|---:|
| Stayed | 26.2 | 22.0 |
| Churned | 86.0 | 85.5 |

Churned customers had substantially higher churn scores than customers who stayed.

The large difference suggests that the churn score can be useful for prioritizing customers who require retention attention.

---

## 5. Customer Satisfaction Is Lower Among Churned Customers

Among customers with recorded support interactions:

| Customer Status | Customers | Average CSAT | Median CSAT |
|---|---:|---:|---:|
| Churned | 6 | 31.67 | 27.5 |
| Stayed | 1 | 90.00 | 90.0 |

Churned customers also recorded complaints and escalations in the support data.

This suggests that poor customer-support experiences and dissatisfaction may be associated with churn.

However, the support sample is small, so this should be treated as a directional finding rather than a definitive causal relationship.

---

## 6. Churned Customers Have Lower CLTV

| Customer Status | Average CLTV | Median CLTV |
|---|---:|---:|
| Stayed | 1,016.47 | 790.0 |
| Churned | 341.17 | 212.5 |

Customers who stayed had substantially higher average and median customer lifetime value.

This highlights the potential financial impact of customer retention and the importance of identifying high-value customers who may be at risk.

---

## 7. Refferal Customers Account for Most Observed Churn

| Subscription Type | Customers | Churned | Churn Rate | Churn Contribution |
|---|---:|---:|---:|---:|
| Organic | 9 | 0 | 0.0% | 0.0% |
| Paid | 6 | 1 | 16.7% | 16.7% |
| Refferal | 6 | 5 | 83.3% | 83.3% |

Refferal customers accounted for **83.3% of observed churn**.

Because the dataset contains only 21 customers, this should be treated as a strong signal for further investigation rather than evidence that the Refferal channel inherently causes churn.

---

## 8. Customer Risk Identification

A customer-level risk analysis was created using the strongest observed churn indicators.

The analysis identified:

- All **6 observed churned customers** as high risk.
- **1 additional customer who stayed** as a high-risk watchlist customer.

The additional customer had a relatively high churn score and a monthly contract but had not yet churned.

This creates an opportunity for the business to intervene **before churn occurs**.

---

# Interactive Visualizations

The project includes six interactive Plotly visualizations:

1. **Contract Type Churn**
2. **Subscription Plan Churn**
3. **Churn Score by Customer Status**
4. **CSAT by Churn Status**
5. **CLTV by Churn Status**
6. **Monthly Customer Churn Trend**

The interactive HTML visualizations are available in:

`charts/interactive/`

Static PNG versions are available in:

`charts/images/`

---

# Business Recommendations

## 1. Strengthen Retention for Monthly Customers

Monthly customers should receive targeted retention strategies such as renewal incentives, loyalty benefits, and proactive engagement before renewal.

## 2. Investigate the Basic Plan

The Basic plan has the highest observed churn rate.

The business should review its pricing, features, and perceived customer value.

## 3. Prioritize High Churn-Score Customers

Customers with high churn scores should be identified early and prioritized for retention outreach.

## 4. Respond to Support Issues Earlier

Customers with repeated complaints, escalations, or low CSAT should receive faster follow-up and stronger issue resolution.

## 5. Protect High-Value Customers

High-CLTV customers showing elevated churn risk should receive priority retention attention.

## 6. Investigate the Refferal Customer Journey

The high observed churn rate among Refferal customers warrants further investigation into onboarding, customer expectations, and service experience.

---

# Project Limitations

The dataset contains only **21 customers**, which is a relatively small sample.

Therefore, the findings should be interpreted as **directional insights rather than definitive conclusions**.

A larger dataset would be required to:

- Validate the observed churn patterns
- Test relationships statistically
- Build a robust predictive churn model
- Improve the reliability of customer-risk segmentation

The support analysis is also based on a small number of customers with recorded support interactions, so the CSAT findings should be interpreted cautiously.

---

# Project Structure

```text
Churn Analysis/
│
├── charts/
│   ├── interactive/
│   │   ├── 01_contract_type_churn.html
│   │   ├── 02_subscription_plan_churn.html
│   │   ├── 03_churn_score_status.html
│   │   ├── 04_csat_churn_status.html
│   │   ├── 05_cltv_churn_status.html
│   │   └── 06_monthly_churn_trend.html
│   │
│   └── images/
│       ├── 01_contract_type_churn.png
│       ├── 02_subscription_plan_churn.png
│       ├── 03_churn_score_status.png
│       ├── 04_csat_churn_status.png
│       ├── 05_cltv_churn_status.png
│       └── 06_monthly_churn_trend.png
│
├── customer_churn_analysis.ipynb
├── customer_churn_data_raw.xlsx
├── README.md
├── .gitignore
└── requirements.txt