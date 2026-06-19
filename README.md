# Credit Risk Analysis
**Credit risk prediction using Python (Logistic Regression) and Power BI**

## Project Overview
Predictive analysis of 150,000 bank clients to estimate the probability of 
serious delinquency within the next 2 years, based on the Kaggle competition 
"Give Me Some Credit".

## Business Problem
Banks need to assess credit risk before approving loans. Approving credit 
for high-risk clients results in financial losses, while rejecting 
low-risk clients results in lost business opportunities.

## Key Findings
- 6.58% of clients present serious delinquency — imbalanced target class
- Delinquent clients are on average 7 years younger (45.9 vs 52.7 years)
- Average income of delinquent clients is $765 lower than non-delinquent
- Late payment history is the strongest predictor — 8x more late payments 
  in delinquent clients
- DebtRatio alone does not predict delinquency accurately

## Model Performance
| Metric | Value |
|--------|-------|
| ROC-AUC | 0.7289 |
| Recall (delinquent) | 62.68% |
| Precision (delinquent) | 12% |
| Accuracy | 68% |

**Note:** Accuracy is not the primary metric due to class imbalance. 
Recall was prioritized since false negatives (undetected delinquent 
clients) represent the highest financial risk for the bank.

## Tools & Technologies
| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data cleaning and preprocessing |
| Scikit-learn | Logistic Regression model |
| Imbalanced-learn (SMOTE) | Class balancing |
| Matplotlib, Seaborn | EDA visualizations |
| Power BI | Interactive dashboard |

## Project Structure
```
credit-risk-analysis/
    ├── data/                          # Raw and processed datasets
    ├── notebooks/
    │   ├── 01_eda.ipynb               # Exploratory data analysis
    │   ├── 02_preprocessing.ipynb     # Cleaning, scaling, SMOTE
    │   └── 03_model.ipynb             # Model training and evaluation
    ├── models/
    │   └── logistic_regression_model.pkl
    ├── powerbi/
    │   └── screenshots/
    └── README.md
```

## Methodology
1. **EDA** — Identified data quality issues (invalid ages, extreme outliers), 
   class imbalance, and key predictive variables.
2. **Preprocessing** — Median imputation for missing values, outlier capping 
   (95th/99th percentile), feature selection (removed multicollinear variables), 
   StandardScaler, and SMOTE for class balancing.
3. **Modeling** — Logistic Regression evaluated with classification report, 
   confusion matrix, and ROC-AUC score.
4. **Power BI Dashboard** — 3-page interactive report covering customer risk 
   profile, model performance, and business recommendations.

## Dataset
- **Source:** [Give Me Some Credit — Kaggle](https://www.kaggle.com/datasets/brycecf/give-me-some-credit-dataset)
- **Size:** 150,000 rows · 11 columns
- **Target variable:** SeriousDlqin2yrs (1 = delinquent, 0 = not delinquent)
