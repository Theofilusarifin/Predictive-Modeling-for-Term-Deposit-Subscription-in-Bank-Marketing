# Predictive Modeling for Term Deposit Subscription in Bank Marketing

## Introduction

### Background

Company X, a financial institution, aims to optimize their term deposit marketing campaign. This campaign is a critical part of their marketing strategy to reach existing and potential customers. However, the resources and investments required for this campaign are significant. Therefore, its success heavily depends on the ability to target the audience most likely to subscribe to term deposits.

### What is Term Deposit?

Term deposits are deposits held at financial institutions with a fixed maturity date or term, commonly referred to as the "term." Term deposits differ from call deposits, such as savings or checking accounts, which can be withdrawn at any time without notice or penalty. Term deposits that require notice for withdrawal effectively function as term deposits, even though they lack a fixed maturity date.

Term deposits are investments with a specified period involving depositing money into an account at a financial institution. Term deposit investments usually have short-term maturities ranging from one month to several years and will have different minimum deposit rates.

Investors should understand that when purchasing term deposits, they can only withdraw their funds after the term has ended. In some cases, account holders may allow investors to terminate or withdraw their funds early if they provide notice a few days in advance. Additionally, there will be penalties for early termination.

## Dataset Overview

- **Number of Records:** 31,647
- **Number of Features:**
  - Numeric: 8
  - Categorical: 10
- **No missing or duplicate data** in the dataset.

## Exploratory Data Analysis (EDA)

### Method Used: Univariate, Bivariate, Multivariate

### Numeric Features Overview

- **Average client age:** 41 years
- **Average balance:** $1364
- **Percentage of clients with negative balance:** 8.42%

## Modeling

### Performance Metrics

| Model              | Precision | Recall | F1-Score |
|--------------------|-----------|--------|----------|
| LightGBM           | 0.630     | 0.510  | 0.560    |
| CatBoost           | 0.630     | 0.480  | 0.540    |
| XGBoost            | 0.590     | 0.480  | 0.530    |
| Random Forest      | 0.650     | 0.390  | 0.490    |
| Decision Tree      | 0.460     | 0.500  | 0.480    |
| Gradient Boosting  | 0.610     | 0.400  | 0.480    |
| AdaBoost           | 0.580     | 0.360  | 0.440    |
| Logistic Regression| 0.610     | 0.320  | 0.420    |
| SVC                | 0.660     | 0.300  | 0.410    |
| Gaussian NB        | 0.320     | 0.580  | 0.410    |
| KNN                | 0.550     | 0.320  | 0.400    |

### Model Selection

LightGBM (LGBM) will be chosen as the model based on the highest F1-score compared to other models in the list.

## Optimization

Parameter optimization on the LightGBM model did not result in improvement, with Precision, Recall, and F1 Score values not significantly changed. However, the model's usage after optimization will still be conducted.

## Feature Importance

From the feature importance results, the top 5 features that most influence the model's prediction are:
1. duration (Positive)
2. month (Negative)
3. contact_unknown (Negative)
4. contact_celular (Positive)
5. housing (Negative)

## Error Analysis

In Error Analysis, the model failed to classify certain data, namely:
- Users who do not have default credit.
- Users who do not subscribe to personal loans.

## Recommendation

### Technical
- Seek additional datasets with more variety to enhance representation and better represent the user population.
- Conduct in-depth review of the features used in the model to ensure relevance and alignment with the desired target.
- Further explore data processing techniques that can improve model performance.

### Business
- Utilize insights from the model to develop more targeted marketing campaigns by targeting customers who are highly likely to subscribe.
- Enhance customer retention strategies by leveraging insights from the model to understand the factors influencing customer decisions to subscribe.

