# Project Overview

The dataset provides detailed sales and order-related information, making it suitable for building a predictive model to estimate order amounts. This project focuses on data cleaning, EDA, feature selection, and model training.

## Data Cleaning

Involves handling missing values, removing irrelevant columns, converting date columns, and addressing negative values in the order amount.

### The following approaches can be applied to handle missing data:

- **Remove Columns or Rows**: If the columns or rows with missing values are not critical, you can drop them.
- **Imputation**:
  - Fill with the mean, median, or mode for numerical data.
  - Use the most frequent value like ("NA") for categorical data.
- **Predictive Imputation**: Use machine learning models to predict the missing values based on other columns.

## Exploratory Data Analysis (EDA)

Performs an initial data inspection, including basic statistics, data distribution, and visualizations using Seaborn and Matplotlib.

## Feature Selection

Using Random Forest Regressor and SelectKBest to identify important features for predicting the target variable.

The Selected Features:
```python
X = df[['Rolls Ordered', 'Est. Extended Cost (Line)', 'Parent Record', 'Actual Ship Date Year', 'Sales Order Name', 'Date Created Year', 'Sales Region', 'Memo', 'Project Use Type']]
y = df['Order Amount']
```

## Model Training and Hyperparameter Tuning

Multiple models, including Linear Regression, Random Forest, Gradient Boosting, and XGBoost, were compared. Random Forest was selected as it provided the best performance.

After training the Random Forest Regressor model, the best hyperparameters were identified through GridSearchCV:

This high R² achieved indicates that the model is performing well, as it captures most of the variance in the Order Amount.

### The visualizations support these results:

- Predicted values closely match actual values, as seen in the scatter plot and histogram.
- Residuals are unbiased and centered around zero.
- Descriptive statistics and results confirm the model's robustness.

## Descriptive Statistics

Descriptive statistics for both the actual and predicted values show a close alignment in their means, with actual values averaging at 8231.98 and predicted values at 8206.42. Both distributions have similar standard deviations, and the maximum and minimum values indicate that the model is capable of handling outliers relatively well.

## Further Investigation

Although the model performs well overall, there are discrepancies in extreme values, as seen in the negative prediction for one of the actual values and the deviation in higher values. Further refinement of the model, particularly for handling outliers and extreme values, could improve prediction accuracy. Additionally, more advanced techniques like outlier detection and robust regression models might be explored for better performance in such cases.

## Conclusion

The Random Forest Regressor model demonstrates strong performance in predicting Order Amount, with a high R² score, indicating it captures most of the variance in the data. The model's predictions closely match the actual values, as seen in the visualizations. Descriptive statistics show that the model handles outliers well. However, discrepancies in extreme values suggest room for improvement, especially in handling outliers. Further refinement and advanced techniques like outlier detection could enhance the model's accuracy.
