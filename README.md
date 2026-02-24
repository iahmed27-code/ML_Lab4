# Lab 4: Data Quality Assessment & Preprocessing

## Task 1: Data Quality Issues Identified
- **Incorrect Data Types:** `Date` and `Amount` were stored as objects.
- **Data Noise:** `Amount` column contained currency symbols (`$`) and commas.
- **Missing Values:** Artificial NaNs were introduced in the `Amount` column.
- **Outliers:** Extreme values were detected in sales revenue.

## Task 2: Missing Value Strategy
**Strategy:** Median Imputation.
**Reason:** We used the median to fill missing values because the dataset contains outliers. The median is more robust than the mean and prevents biased estimates.

## Task 3: Outlier Handling
**Method:** Interquartile Range (IQR).
**Action:** Values outside `[Q1 - 1.5*IQR, Q3 + 1.5*IQR]` were removed to ensure the model isn't distorted by extreme transactions.

## Task 4: Normalization vs. Standardization
- **Min-Max Scaling:** Rescaled features to a range of [0, 1]. Best for distance-based algorithms like KNN.
- **Z-score Standardization:** Centered data around a mean of 0 with a standard deviation of 1. Best for PCA and Linear Regression.

## Task 5: PCA Interpretation
- **Result:** The explained variance ratio was distributed almost equally between PC1 and PC2.
- **Interpretation:** This indicates low correlation between `Amount` and `Boxes Shipped`. PCA showed that both features provide unique information.
