# Lung Cancer Survey Classification


## Abstract

This project builds and compares binary classification models for predicting
lung cancer status from survey-based patient features. The workflow includes
data loading, missing-value inspection, outlier capping, categorical encoding,
feature scaling, feature selection, stratified cross-validation, and model
comparison.

## Objective

The objective is to predict the `LUNG_CANCER` class using survey features such
as smoking, coughing, chest pain, shortness of breath, allergy, wheezing, and
swallowing difficulty.

## Dataset

The dataset contains 309 samples and 16 columns. The target column is
`LUNG_CANCER`, with two classes:

- `YES`
- `NO`

The dataset has no missing values, but it is strongly imbalanced toward the
`YES` class.

## Preprocessing

The preprocessing workflow includes:

1. Strip whitespace from column names.
2. Check missing values.
3. Cap numerical outliers using the IQR rule.
4. Encode categorical variables with label encoding.
5. Split data with stratification.
6. Scale features with `StandardScaler`.
7. Select the top 8 features with ANOVA F-test.

## Models

The following models are compared:

- Logistic Regression
- Decision Tree
- Random Forest
- Extra Trees
- AdaBoost
- Gradient Boosting
- Gaussian Naive Bayes
- SVC with linear kernel
- SVC with RBF kernel
- KNN
- Linear Discriminant Analysis
- XGBoost
- MLP neural network

## Final Recorded Results

| Model | Accuracy Mean | Accuracy Std | F1 Mean | F1 Std |
|---|---:|---:|---:|---:|
| DecisionTree | 0.8925 | 0.0091 | 0.9382 | 0.0059 |
| RandomForest | **0.9056** | 0.0177 | 0.9466 | 0.0100 |
| ExtraTrees | 0.8958 | 0.0088 | 0.9407 | 0.0052 |
| AdaBoost | 0.8992 | 0.0204 | 0.9443 | 0.0105 |
| GradientBoosting | 0.8990 | 0.0134 | 0.9425 | 0.0080 |
| GaussianNB | 0.8892 | 0.0079 | 0.9372 | 0.0049 |
| SVC linear | 0.8926 | 0.0238 | 0.9408 | 0.0121 |
| SVC rbf | 0.9024 | 0.0192 | 0.9455 | 0.0105 |
| KNN | 0.8959 | 0.0266 | 0.9419 | 0.0136 |
| XGBoost | **0.9056** | 0.0209 | **0.9468** | 0.0117 |
| MLP | **0.9056** | 0.0134 | **0.9468** | 0.0074 |

## Conclusion

Random Forest, XGBoost, and MLP achieved the highest recorded mean accuracy.
XGBoost and MLP achieved the highest recorded mean F1-score. AdaBoost achieved
the highest recall, which may be valuable in a medical screening setting.

Because the dataset is small and imbalanced, the results should be interpreted
carefully. Future improvements could include class weighting, SMOTE, threshold
tuning, more robust validation, and testing on an external dataset.
