# diabetes_detection

## Background

The aim of this project is to develop an end-to-end machine learning pipeline to classify diabetes risk into three categories: Low, Moderate and High.

The project uses a dataset from Kaggle containing demographic, lifestyle and clinical features. It provides an opportunity to practise data preprocessing, exploratory data analysis, feature engineering, model development and evaluation.

This project is a work in progress, with future improvements planned around model comparison, experiment tracking and deployment.

### Dataset

Source: [Diabetes Risk Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/mansiaggarwal88/diabetes-risk-prediction)

The dataset includes numerical and categorical features, as well as missing values that require investigation and appropriate handling.

## Exploratory Data Analysis

- **Feature relationships:** Fasting blood sugar, HbA1c, BMI, waist circumference and blood pressure tend to increase with diabetes risk. BMI and waist circumference are strongly correlated, as are fasting blood sugar and HbA1c, suggesting some overlap in the information these features provide.
- **Missing values:** Alcohol consumption has a relatively high proportion of missing values, with smaller amounts of missing data in other lifestyle variables. Removing incomplete rows could discard useful data, so different imputation strategies were considered.
- **Categorical distributions:** Smoking status, income bracket and alcohol consumption have uneven category distributions, which were considered when selecting preprocessing strategies.
- **Class distribution:** The target classes are not severely imbalanced, but performance should still be assessed using per-class precision, recall, F1-scores and a confusion matrix.
- **Feature distributions:** Histograms and box plots reveal skewness and potential outliers in some numerical features. These were investigated to inform preprocessing decisions.

## Preprocessing

Preprocessing is performed after the train/test split to avoid data leakage.

- **Missing values:** Numerical features are imputed using the mode. Categorical features are imputed using the most frequent category, where appropriate. Alcohol consumption is assigned a separate `Missing` category due to its higher proportion of missing values.
- **Categorical encoding:** Categorical features are one-hot encoded to make them suitable for machine learning models.
- **Feature scaling:** Numerical features are scaled where appropriate, depending on the algorithm being used.
- **Data splitting:** Stratified splitting is used to preserve the target class distribution across training and test sets.


## Next Steps and Future Improvements

- **Model evaluation:** Generate predictions on the test set and evaluate performance using appropriate classification metrics, including macro F1, precision, recall and a confusion matrix.
- **Feature engineering:** Investigate additional features and transformations that could improve predictive performance, guided by exploratory data analysis and domain knowledge.
- **Model experimentation:** Establish baseline performance and compare different algorithms, including Random Forest and gradient boosting models.
- **Experiment tracking and model monitoring:** Integrate MLflow to track experiments, compare model performance, log parameters and metrics, and explore model versioning. Investigate monitoring for data drift and changes in predictive performance over time.
- **Scalability and deployment:** Explore alternative data storage approaches and development platforms, such as Azure DevOps, to support a more scalable, automated end-to-end ML workflow.
- **Domain knowledge and feature development:** Investigate additional risk factors for Type 2 diabetes that are not represented in the current dataset, such as family history and genetic predisposition. This will involve reviewing relevant research papers and, where possible, consulting domain experts to inform feature selection and future iterations of the project.

  For context, Diabetes UK discusses several factors associated with Type 2 diabetes: [Causes of Type 2 diabetes](https://www.diabetes.org.uk/about-diabetes/type-2-diabetes/causes).