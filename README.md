# Kaggle Cardiovascular Disease and Smoking: Data Science Project

## Overview
This project explores the relationship between Cardiovascular Disease (CVD) and key factors such as Smoking, Body Mass Index (BMI), Age, and Gender using a dataset of 70,000 individuals. The project involves data preprocessing, exploratory data analysis, and modeling using both Generalized Linear Models (GLMs) and Nonparametric Methods.

## Features of the Dataset
The dataset contains the following columns:

- **id**: Unique identifier
- **age**: Age of the individual
- **gender**: Gender (1 = Female, 2 = Male)
- **height**: Height in centimeters
- **weight**: Weight in kilograms
- **ap_hi** and **ap_lo**: Systolic and diastolic blood pressure
- **cholesterol**: Cholesterol levels (1 = Normal, 2 = Above Normal, 3 = Well Above Normal)
- **gluc**: Glucose levels (1 = Normal, 2 = Above Normal, 3 = Well Above Normal)
- **smoke**: Smoking status (1 = Smoker, 0 = Non-Smoker)
- **alco**: Alcohol intake (1 = Yes, 0 = No)
- **active**: Physical activity status (1 = Active, 0 = Inactive)
- **cardio**: Presence of cardiovascular disease (1 = Yes, 0 = No)

## Exploratory Data Analysis

### Age and Cardiovascular Disease
A density plot contrasts the age distributions for individuals with and without CVD.

#### Key Insights:
- Younger ages show a higher prevalence of CVD-free individuals.
- Older ages show a higher prevalence of CVD-affected individuals.
- The likelihood of CVD increases with age, particularly from the mid-40s.

### BMI and Cardiovascular Disease

#### BMI Calculation:
```python
df['BMI'] = df['weight'] / ((df['height'] / 100) ** 2)
```
### BMI Histogram:
Visualizes the BMI distribution for individuals with and without CVD.

#### Observations:
- Higher BMIs are more common among individuals with CVD.
- The histogram reveals a clear relationship between increased BMI and the likelihood of CVD.

### Gender and Smoking
A stacked bar chart shows smoking habits by gender.

#### Observations:
- Smoking is more prevalent among men than women.
- Highlights the need for gender-specific smoking cessation programs.

## Modeling

### Generalized Linear Models (GLMs)

- **Linear Regression**: Predicts real-valued outputs.
  - Features used: age, gender, BMI, ap_hi, gluc, smoke.
  - Results:
    - Training RMSE: 0.479
    - Test RMSE: 0.477

- **Logistic Regression**: Predicts binary outcomes (cardio presence).
  - Features used: age, gender, BMI, ap_hi, gluc, smoke.

- **Poisson and Negative Binomial Regression**: Used for count data.

### Nonparametric Methods

- **Decision Tree Classifier**:
  - Splits the data based on feature thresholds.
  - Accuracy: 63.6%
  - ROC-AUC: 64.1%

- **Random Forest Classifier**:
  - Combines multiple decision trees for better predictions.
  - Accuracy: 65.9%
  - ROC-AUC: 72.2%

- **Decision Tree Regressor**: Predicts continuous values.
  - Results:
    - Training RMSE: 0.165
    - Test RMSE: 0.591

## Key Findings

### Age and CVD:
- Age is a strong predictor of CVD, with prevalence increasing in older populations.

### BMI and CVD:
- Higher BMI is associated with a higher likelihood of CVD.

### Smoking and Gender:
- Smoking prevalence is significantly higher in males, emphasizing the importance of targeted health policies.

### Modeling Insights:
- Random Forest models performed better than Decision Trees and GLMs for classification tasks.

## Visualizations
1. **Age and CVD**
2. **BMI and CVD**
3. **Gender and Smoking**

## Conclusion
This project highlights the significant relationships between cardiovascular disease and factors like age, BMI, and smoking. The modeling results suggest that nonparametric methods like Random Forests are more effective for predicting cardiovascular disease than generalized linear models.

## Technologies Used
- **Programming Language**: Python
- **Libraries**:
  - Data Analysis: pandas, numpy
  - Visualization: matplotlib, seaborn
  - Machine Learning: scikit-learn

## Future Directions
- Incorporate additional health metrics for enhanced predictions.
- Explore deep learning models for improved classification.
- Analyze temporal trends in CVD occurrence.

## Acknowledgments
Special thanks to the CDC healthcare dataset providers and the datasets from Kaggle for making this analysis possible.
