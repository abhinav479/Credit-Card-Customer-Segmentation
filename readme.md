# Credit Card Customer Segmentation Project

## Overview

This project performs customer segmentation on a credit card dataset to identify distinct groups of customers based on their behavior and financial attributes. The goal is to provide actionable insights for targeted marketing, customer retention, and risk management — key priorities for financial service companies like American Express.

***

## Dataset

- The dataset contains anonymized data for 8,950 credit card customers.
- Features include balances, purchase patterns, payment behavior, cash advances, credit limits, and tenure.
- Source: [Kaggle Credit Card Customer Segmentation Dataset](https://www.kaggle.com/code/danielsimamora/credit-card-customer-segmentation)

***

## Project Steps

### 1. Data Loading and Cleaning
- Loaded the dataset and set `CUST_ID` as the index.
- Examined data for missing values, duplicates, and inconsistencies.
- Imputed missing values in key columns (`MINIMUM_PAYMENTS`) with median values to maintain data integrity.

### 2. Exploratory Data Analysis (EDA)
- Visualized distributions of important features (balance, purchases, cash advances).
- Checked feature correlations to understand underlying relationships.
- Identified outliers using boxplots to assess data variability and prepare for scaling.

### 3. Feature Engineering
- Created new ratio-based features such as payment-to-balance ratio, credit utilization, and purchase type ratios to capture deeper customer behavior insights.
- These engineered features enrich the dataset for more nuanced clustering.

### 4. Feature Scaling
- Standardized features using `StandardScaler` to normalize data ranges.
- Scaling ensures fair treatment of all features in distance calculations within clustering algorithms like K-Means.

### 5. Clustering (K-Means)
- Applied K-Means clustering using an elbow plot to select the optimal number of clusters (`k=4` chosen).
- Assigned cluster labels to customers, creating distinct groups based on behavior and financial traits.

### 6. Cluster Profiling and Interpretation
- Generated summary statistics per cluster for all key features.
- Interpreted clusters with business-relevant names such as “High Spenders,” “Low Activity,” and “High Risk”.
- Suggested marketing and risk management strategies tailored to each customer segment.

### 7. Visualization
- Created bar charts to compare feature averages across clusters.
- Used pie charts to show cluster size distribution for easy stakeholder communication.


## Customer Segment Profiles

| Cluster | Average Balance | Average Purchases | Cash Advance | Credit Utilization | Payment to Balance Ratio | Description                          | Number of Customers |
|---------|-----------------|-------------------|--------------|--------------------|--------------------------|------------------------------------|---------------------|
| 0       | 6008            | 3280              | 4531         | 0.59               | 12.18                    | High Balance and Cash Advance Users; indicating possible high credit usage but risk | 774                 |
| 1       | 341             | 1060              | 83           | 0.08               | 31.13                    | Loyal Spenders with lower balances and frequent payments, good payback behavior | 4006                |
| 2       | 1895            | 57                | 1739         | 0.59               | 3.78                     | Low Purchases but high cash advances, possibly credit revolvers | 2143                |
| 3       | 1937            | 1021              | 587          | 0.71               | 1.01                     | Moderate users with relatively high credit utilization but lower payment ratios | 2027                |

***

## How to Run This Project

### Dependencies
- Python 3.x
- pandas
- scikit-learn
- matplotlib
- seaborn

Install required libraries:
```bash
pip install pandas scikit-learn matplotlib seaborn
```

### Steps
1. Clone the repository.
2. Load and clean the dataset.
3. Perform EDA and feature engineering.
4. Scale features and run K-Means clustering.
5. Analyze and visualize cluster profiles.
