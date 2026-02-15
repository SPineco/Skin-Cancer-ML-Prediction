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

To set up for modeling, the dataset was split into a testing and training set, with the traning set oversampling the minority class to adjust for skewness. The following is a picture of the initial set up:

<img width="1423" height="636" alt="image" src="https://github.com/user-attachments/assets/f94fb6ca-b9ea-4d08-8713-6937eb73a72a" />

The purpose of initial model was to get a baseline measure for model perform as well as examine which features are the most significant in order to conduct feature engineering. A simple logistic regression and logit model did not find any useful information in regards to significant variables, however a decision tree found that the age binaries and the race_white binary were significant predictors of skin cancer. This makes sense due to the chances of skin cancer increasing with age and with paler skin. This will help lead us in how we conduct feature engineering. Below is a picture of a feature importance graph from the decision tree:

<img width="997" height="672" alt="image" src="https://github.com/user-attachments/assets/1a1b8a44-a0e1-460a-9120-c195ed88dc9a" />

<img width="1341" height="676" alt="image" src="https://github.com/user-attachments/assets/7ba439e9-bd94-4348-9c7e-1c949b344140" />

## Feature Engineering

For later models, data engineering will be utilized. The main difference between this engineering and the cleaning/transformation performed earlier is that the following variables were turned ordinal through rankings: genhealth, diabetic, and AgeCategory. Additionally, new variables, such as Old_Smoker and Chronic Count, were created that combined different health conditions and habits. The most important variable that was created was UV_Risk, which accounted for age, pale skin, and exercise. Overall, the new engineered dataset had 30 variables, which is 12 more than the original set. 

## Modeling

Several different techniques were utilized to model the data. Grid search, random grid search, and a custom scorer for cross-validation metrics are some examples. Several models were created including a random forest, several decision trees with differing metrics, and an XgBoost model. The results of these models can be seen in the following table:

| Model                            | Accuracy | Recall |
|----------------------------------|----------|--------|
| Grid Search Decision Tree        | 61.29%   | 86.02% |
| Random Forest                    | 72.80%   | 66.35% |
| Neural Network                   | 90.58%   | 0.00%  |
| Decision Tree with custom scorer | 61.29%   | 86.02% |
| XgBoost                          | 65.40%   | 82.49% |

As you can see via the table, the highest recal generated was by the Grid Search Decision Tree and the Decision Tree with the custom scorer. The model recommeded for deployment is the Grid Search Decision Tree, as it has both high recall and is cross validated. The following confusion matrix was created to showcase the number of cases the model correctly and incorrectly predicts:

<img width="821" height="515" alt="image" src="https://github.com/user-attachments/assets/752eacc0-bbf4-4f44-84b4-7f9412719044" />

Out of 63,959 cases, the model minimizes the number of missed real diagnosis at the cost of have a high number of false positive. As such, it is recommended that the model be utilized as an early screening tool of cancer, rather than for actual diagnosis. With such a model, skin cancer can be detected earlier and treatment can begin much faster, saving many lives. 

For more information in regards to the code, please access the Skin Cancer Machine Learning.ipynb file: https://github.com/SPineco/Skin-Cancer-ML-Prediction/blob/main/Skin%20Cancer%20Machine%20Learning.ipynb. 




