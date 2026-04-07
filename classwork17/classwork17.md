# Classwork 17: Income Prediction Model

In this assignment, you will build a model to predict whether a person’s income is:

- `<=50K`  
- `>50K`  

This is a binary classification problem using census data.

---

## Data Provided

You are given two datasets:

### 1. Labeled dataset (for building your model)
- **File:** `census_labeled.csv`: https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/census_labeled.csv  
- Includes both features **and** the target variable `income`

You should use this dataset to:
- Explore the data
- Train your model
- Evaluate your model (e.g., train/test split, cross-validation, etc.)

> **Important:** You are expected to split this dataset yourself into training/validation/test sets if needed.

---

### 2. Unlabeled dataset (for final predictions)
- **File:** `census_unlabeled_features.csv`: https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/census_unlabeled_features.csv  
- Contains the same features, but **does NOT include `income`**

Your task is to:
- Use your trained model to predict `income` for this dataset

---

## Goal

Your goal is to produce the most accurate predictions possible on the **unlabeled dataset**.  

Your predictions will be evaluated based on **accuracy** compared to the true (hidden) values.

---

## Modeling

You are free to choose any approach, including:
- Logistic regression
- Decision trees
- Random forests
- Other models

You may evaluate your model using:
- Train/test split
- Cross-validation
- Any other method

---

## Important Note on Class Imbalance

The labeled dataset is **imbalanced**:
- 415 observations: `<=50K`
- 85 observations: `>50K`

However, the evaluation dataset (the unlabeled one) will be:
- **Balanced (50/50 split)**

---

## What to Submit

### 1. Notebook (HTML)
- Export your notebook as an **.html file** and upload it to Canvas. This should show your process (exploration, modeling, evaluation)

---

### 2. Predictions CSV (Google Form)

Submit a CSV file to:  
https://forms.gle/VSkRP21Rbq7Q6fFb7

Your file must:
- Match the format shown in this example (though with your own values): https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/prediction_example_format.csv  
- It should only include the columns `id` and `income`

---

## Files

- Labeled data:  
  https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/census_labeled.csv  

- Unlabeled data (for prediction):  
  https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/census_unlabeled_features.csv  

- Example submission format:  
  https://github.com/juliaolivieri/COMP_162_2026/blob/main/classwork17/prediction_example_format.csv  
