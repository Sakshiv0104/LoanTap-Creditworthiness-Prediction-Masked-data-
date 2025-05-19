# LoanTap-Creditworthiness-Prediction-Masked-data
# 🏦 LoanTap Creditworthiness Prediction – SQUAD Datathon 2025

This project was created for the **SQUAD Datathon 2025**, where the objective is to predict whether a credit line should be extended to an individual, based on anonymized features. The task is grounded in a real-world financial application — **LoanTap's** underwriting process for evaluating **Personal Loan** eligibility.

---

## 🧾 Problem Statement

**Context**  
[LoanTap](https://loantap.in) is a fintech platform delivering customized loans to millennials. Their products include:

- Personal Loan
- EMI Free Loan
- Personal Overdraft
- Advance Salary Loan

The challenge here focuses on **underwriting for Personal Loans** — determining if an individual is creditworthy enough for a credit line based on certain attributes.

**Goal**  
Given a set of anonymized features for an individual (`X1` to `X19`), predict whether a loan should be extended (`Y = 1`) or not (`Y = 0`).

---

## 📁 Dataset Description

This is a **binary classification** problem with no prior information about feature meanings. It encourages exploratory data analysis (EDA) to uncover hidden patterns.

| File | Description |
|------|-------------|
| `train.csv` | Training dataset with features `X1` to `X19` and target `Y` |
| `test.csv` | Test dataset with same features, without target |
| `sample_submission.csv` | Format for submission: `ID`, `Y` |

- `X1`–`X19`: Anonymous features (categorical or numerical)
- `Y`: Target label (1 = loan approved, 0 = rejected)

---

## 💡 Evaluation Tips (As per competition)

To **score high points**:

✅ Perform **EDA** on each feature and write key **insights**.  
✅ **Clean** and preprocess the data properly.  
✅ Avoid any form of **data leakage** — doing so will cost modeling points.  
✅ Tune your models to improve generalization and performance.  
✅ Submit predictions sorted by **ID in ascending order**.  
✅ Write **clean, well-commented code** (2 bonus points!).

---

## 🔬 Solution Approach

### 1. 🧼 Data Cleaning
- Encoded categorical variables using `LabelEncoder`
- Handled missing/null values (if any)
- Scaled numerical values with `StandardScaler`

### 2. 📊 Exploratory Data Analysis (EDA)
- Plotted feature distributions (histograms, boxplots, countplots)
- Identified categorical features via unique value counts
- Analyzed correlation between features and target variable
- Applied **Chi-Square Test** to measure importance of categorical variables

### 3. 🤖 Modeling
- Trained multiple models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost
  - **Neural Network (MLPClassifier)** ← Final chosen model

- Used `GridSearchCV` for hyperparameter tuning
- Evaluated models with metrics:
  - Accuracy
  - F1-Score
  - Precision & Recall
  - Confusion Matrix

### 4. 🏁 Final Submission
- Generated predictions on `test.csv` using the best model
- Created `submission.csv` in correct format
- Sorted rows by `ID` before submission

---

## 🧪 Sample Submission Format

```csv
ID,Y
0,1
1,0
2,1
...

