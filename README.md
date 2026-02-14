# Skin-Cancer-ML-Prediction

## Summary
The purpose for this project is to create a language model that can predict skin cancer within patients. The dataset analyzed is concerned with skin cancer and the factors that influence it, such as chronic illness, exercise, and age. The target variable of the dataset is Skin Cancer and is heavily skewed with 9.32% of paticipants having cancer. Different techniques, such as class weights and feature engineering, were utilized to account for this skewness. Additionally, the metric "recall" was chosen to be Various models, such as decision trees, random forest, and logistic regression, were trained and tested to differing results. The best model was a decision tree found through random search that scored a recall score of 86.02%. This means that the model reduces the costs of missed diagnostic, thus increasing profit.

## Dataset Information
The dataset contains the following variables:

| Variable |
|-----------|
| Heart Disease |
| BMI |
| Smoking |
| Alcohol Consumption |
| History of Stroke |
| Physical Health |
| Mental Health |
| Difficulty Walking |
| Sex |
| Age Category |
| Race |
| Diabetes Status |
| Physical Activity |
| General Health |
| Sleep Time |
| Asthma |
| Kidney Disease |
| Skin Cancer |

The dataset contains 18 variables with Skin Cancer being the target variable. There are 319,795 instances within the dataset, and the target variable is heavily skewed with the positive class being in the minority. To aid in analysis and prediction, several of the variables are transformed, either into binaries or dummies. The code for this can be seen down below:

<img width="1321" height="618" alt="image" src="https://github.com/user-attachments/assets/75f098c0-053a-4b3a-8aa8-a6db80b33217" />

## Initial Modeling
