# predict-customer-default
## Project Details
**Goal:** Building a credit scoring model predicting the probability that somebody will experience financial distress in the next two years. This project can be applied to any domain that relies on the historical credit history of the user to identify if they are likely to default or not on their new loan/credit. Given the need to have model explainability to back up the credit decisions, only white-box-based modeling approaches were in the running.

**Target AUC:** 0.86955

**Achieved AUC:** 0.85898

**Model:** Crossvalidated XGBoost model. Achieved best performance through the parameter tuning of `scale_pos_weight` and `n_estimators`.

<br />

## **Data Preprocessing aspects incorporated:**
1. Handle Class Imbalance: Cost-based approach

2. Handling Missing Data Points: KNN-based imputation

3. Ways to detect Outlier: Extreme Value Analysis _(Less than Q1+1.5 * IQR or greater than Q3+1.5 * IQR)_

4. Handling outliers:\
a. Remove them\
b. Impute them with values\
c. Use fixed-width binning\
d. Use adaptive binning\
e. Normalize or Standardize the features

5. Identifying features correlation

<br />

## **ML Models evaluated:**
1. Logistic Regression: Balanced `class_weight` approach
2. Random Forest Model: Increased `n_estimators`
3. XGBoost: `scale_pos_weight`, `n_estimators`
4. Linear Kernel SVM: `Balanced class_weight`
5. Neural Network: Vanilla implementation
