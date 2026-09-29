## Bank Account Activity and Customer Retention Analysis

## Project Overview

This project analyzes bank account data to identify patterns associated with account activity, inactivity, and closure.

The analysis focuses on account status, account type, branch, account balances, account tenure, opening dates, and customer-level account behavior.

The objective is to generate evidence-based insights that can help a bank better understand account activity and identify areas that may require further investigation.

## Business Problem

A bank has a large portfolio of customer accounts, but not all accounts remain active. Some accounts become dormant, while others are closed.

Management needs to understand:
- How accounts are distributed across active, dormant, and closed statuses.
- Whether account balances differ across account statuses.
- Whether customers with multiple accounts exhibit different status patterns.
- Whether branch, account type, balance, or account tenure is associated with account status.
- Which findings are supported by statistical evidence.

This project uses exploratory data analysis and statistical testing without making unsupported assumptions about customer behavior.

## Dataset

The dataset contains **95,000 bank account records** and the following variables:

| Column | Description |
|---|---|
| `account_id` | Unique account identifier |
| `customer_id` | Customer identifier |
| `branch_id` | Bank branch identifier |
| `account_type` | Type of bank account |
| `balance` | Account balance |
| `open_date` | Account opening date |
| `status` | Account status |

The dataset contains **47,640 unique customers** and **150 branches**.

### Account Status Categories
- Active
- Dormant
- Closed

## Data Preparation

The analysis included:
- Dataset structure and data types
- Missing-value checks
- Date conversion and validation
- Duplicate checks
- Account-ID uniqueness checks
- Account-status distribution
- Balance summary statistics
- Customer-level account profiling

No invalid dates were found after conversion, and no duplicate account IDs were identified.

## Analysis Approach

### 1. Data Quality Assessment
- Dataset dimensions
- Missing values
- Data types
- Duplicate records
- Date validation

### 2. Descriptive Analysis
- Account-status distribution
- Account types
- Branch distribution
- Balance statistics
- Account opening dates

### 3. Balance Analysis
- Mean and median balances
- Balance distribution by status
- Quartile analysis

### 4. Customer-Level Analysis

Customers were classified into:
- **Active only**
- **Inactive only**
- **Mixed status**

This moves the analysis beyond individual accounts to customer-level behavior.

### 5. Statistical Testing

| Analysis | Test |
|---|---|
| Branch vs Status | Chi-square |
| Account Type vs Status | Chi-square |
| Balance vs Status | Kruskal-Wallis |
| Tenure vs Status | Kruskal-Wallis |

A significance level of **0.05** was used.

## Key Findings

### Account Status

- **Active:** 80,707 accounts (84.95%)
- **Dormant:** 9,526 accounts (10.03%)
- **Closed:** 4,767 accounts (5.02%)

Therefore, **15.05% of accounts are either dormant or closed**.

This identifies a meaningful segment for further investigation, but the data does not establish why these accounts became inactive or closed.

### Customer Profiles

- **Active only:** 34,899 customers
- **Mixed status:** 9,478 customers
- **Inactive only:** 3,263 customers

Mixed-status customers have a median of **3 accounts**, compared with 2 for active-only customers and 1 for inactive-only customers.

### Customer Balances

| Customer Profile | Median Total Balance |
|---|---:|
| Mixed status | 114,592.96 |
| Active only | 62,305.98 |
| Inactive only | 34,536.91 |

Mixed-status customers represent a relatively high-balance customer segment in this dataset.

### Statistical Evidence

| Analysis | Test | Statistic | p-value |
|---|---|---:|---:|
| Branch vs Status | Chi-square | 338.84 | 0.05 |
| Account Type vs Status | Chi-square | 5.39 | 0.71 |
| Balance vs Status | Kruskal-Wallis | 0.62 | 0.73 |
| Tenure vs Status | Kruskal-Wallis | 2.19 | 0.33 |

The account-type, balance, and tenure tests did not provide statistically significant evidence at the 0.05 level.

The branch-status result is close to the chosen threshold and should therefore be investigated further rather than treated as definitive evidence of a business effect.

## Business Implications

Based on the analysis, a bank could consider:
1. Investigating dormant and closed accounts to understand the factors associated with inactivity.
2. Segmenting customers by account-status profile.
3. Examining mixed-status customers more closely because this group has more accounts and higher median total balances.
4. Conducting deeper branch-level analysis before making branch-specific decisions.
5. Collecting transaction, demographic, product, and customer-feedback data to investigate the reasons behind inactivity.

These are analytical implications, not causal conclusions.

## Visualizations

The project includes:
- Account status distribution
- Customer status profiles
- Median balance by customer status profile
- Median number of accounts by customer status profile
- Branch-level analysis where supported by the data

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

## Project Structure

```text
bank-account-analysis/
├── data/
│   └── accounts.csv
├── notebooks/
│   └── bank_account_analysis.ipynb
├── images/
├── .gitignore
├── README.md
└── requirements.txt
```

## How to Run

```bash
git clone https://github.com/albertbijabibola/bank-account-analysis.git
cd bank-account-analysis
pip install -r requirements.txt
jupyter notebook
```

Open the notebook in the `notebooks` directory and run the cells sequentially.

## Limitations

- No transaction-level behavior is available.
- Customer demographics are not available.
- The analysis cannot determine the actual reasons for dormancy or closure.
- Association does not imply causation.
- Additional customer, transaction, product, and branch data would support deeper retention analysis.

## Future Analysis

Possible extensions include:
- Transaction-frequency analysis
- Customer segmentation
- Churn prediction
- Account closure prediction
- Time-series analysis
- Branch performance analysis
- Machine-learning models for inactivity risk
- Customer lifetime value analysis

## Author

**Albert Bijabibola**

Data Science / Data Analytics Portfolio Project

GitHub: `https://github.com/albertbijabibola`
