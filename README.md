"Customer Churn Analysis"

A Python-based exploratory data analysis project that examines customer churn using data pulled from a SQLite database. The project covers data extraction, cleaning, merging, KPI calculation, and visualization to uncover the key drivers behind customer churn.

 Project Overview

Customer churn — when a customer stops using a service — is one of the most important metrics for subscription-based businesses. This project analyzes customer, subscription, and support data to:

Calculate core churn and retention KPIs
Identify which customer segments (plan type, state, contract type) churn the most
Explore the relationship between customer support escalations and churn
Visualize churn trends over time and across customer attributes
Data Cleaning & Preparation
Renamed/dropped irrelevant columns (e.g. interests, pincode)
Standardized inconsistent categorical values (e.g. Men/Women → Male/Female)
Converted date columns to proper datetime types
Filled missing country values by mapping from state
Deduplicated support records per customer (keeping the most recent complaint) and engineered a complaint_count feature
Merged all three tables into a single analysis-ready dataframe on customerid
Engineered features: churn_flag, tenure_days, and a categorical churn_risk bucket (low/med/high) based on churn_score
📊 Key Metrics & Findings
Metric	Value
Churn Rate	28.57%
Retention Rate	71.43%
Average Revenue Per User (ARPU)	₹18.85
Average Customer Tenure	1,493 days
Revenue at Risk	₹73.94K
Escalation Rate	19.05%
Avg. Complaints per User	0.43
Correlation: Escalations vs. Churn	0.77 (strong positive)

Churn rate by plan type:

Plan Type	Churn Rate
Basic	60.00%
Standard	22.22%
Premium	14.29%

Key insight: Customers on the Basic plan churn at more than 4x the rate of Premium customers, and support escalations are strongly correlated with churn (0.77), suggesting that unresolved complaints are a major churn driver.

📈 Visualizations

The notebook includes the following charts (built with matplotlib and seaborn):

Monthly churn trend line chart
Churn rate by plan type (bar chart)
Churn rate by state (bar chart)
Correlation heatmap of encoded features (plan type, contract type, churn score, escalations, churn risk)
Pairplot of encoded numerical/categorical features
Churn risk breakdown by plan type, monthly charges, and gender (categorical plot)
Pivot tables summarizing churn rate and revenue by plan type
🛠️ Tech Stack
Python 3
pandas & numpy – data manipulation
matplotlib & seaborn – data visualization
sqlite3 – database querying
