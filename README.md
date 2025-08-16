# EDA and premium price prediction from an Insurance Dataset
## Contents
1. Problem Statement
2. Target Metrics 
3. Exploratory Data Analysis(EDA) Steps
4. Hypothesis Testing Steps
5. Inferences and Recommendations from EDA and Hypothesis Testing
6. Data Preprocessing and Model Training
7. Model Deployment


## 1. Introduction
From the given dataset, identify the primary factors dominating the cost of the premium for the insurance of the individual. Identify critical insights which can help in designing tailor made proposals and incentivize individuals who are health conscious and have lower probability of placing claims. Train a model to predict the insurance premiums for an individual given the features of the individual used for training the model. Make recommendations based on the analysis done on the dataset to ensure the insurance company is able to strike the optimum trade off between premium amount and probability of a claim.

## 2. Target Metrics
As this is regression problem, the following 4 metrics were used to assess the performance of the models
* Mean Absolute Error
* Mean Squared Error
* R2 Score
* Adjusted R2 Score

## 3. Exploratory Data Analysis(EDA) Steps
The following tasks were executed to obtain insights from the underlying data:
1. Understand the initial aspects of the data like no. of data points and features, no. of null values, understand the feature data types and identify the outliers
2. Univariate analysis like understanding the distribution of the continuous numerical data through KDE plot and understanding the data distribution across different classes of categorical features
3. Creation of new feature 'BMI' using the Height and Weight features
4. Binning of Age and BMI feature
5. Multivariate analysis to understand the relationship between features and to identify the impact of each and every feature on the target feature

## 4. Hypothesis Testing Steps
The following hypothesis testing was done to substantiate the observations made during EDA exercise:
1. Validate the impact of binary health condition features like Diabetes, Chronic Illness etc. on Premium Price inflation
2. Validate the impact of number of Surgeries on premium price inflation
3. Validate the correlation between Chronic Illness and Cancer History

## 5. Inferences and Recommendations from EDA and Hypothesis Testing
Based on the EDA and Hypothesis Testing exercise, the following Inferences were drawn
1. Major surgeries and Transplants are the key factors which spikes up the premium cost
2. Apart from Allergy all other factors like Diabetes, Blood Pressure Issues, Chronic diseases etc. does add up to premium inflation
3. Presence of chronic diseases doesn't mean that the individual is prone to cancer
4. BMI doesn't have any major say in premium variation
5. There is a higher probability of an individual in higher age group having undergone a major surgery

Based on the above inferences, the following recommendations were made
1. Diabetes and Blood Pressure issues are life style diseases which are mostly correctable by simple life style changes. Even though the individual is charged with inflated premium due to these, they can be offered concessions in future premiums if they they show positive changes in their medical reports suggesting incorporation of desirable life style changes.
2. If someone has a history of cancer in their family, they can be offered Cancer treatment riders
3. Individuals with higher age group should be investigated for major surgeries
4. Individuals with chronic illness and transplants can be offered frequent hospitalization riders

## 6. Data Preprocessing and Model Training
The following tasks were done for data preprocessing:
1. The data was split across input vs output features and training vs testing dataset. 
2. The continuous numerical features were scaled using standard scaler. 
3. The categorical features were one hot encoded.

Post data preprocessing four models namely, Linear Regressor, Random Forest Regressor, Gradient Boosting Regressor and XG Boost Regressor models were trained. Given below are the performance on the test dataset for all these models.
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Model performance")

Based on the above data, it was concluded that the Random Forest Model has the best performance on unseen data. So it was saved in a pickle file to be used in a python application for premium price prediction.

## 7. Model Deployment
The pickle files produced during the model training was used in a flask application to be loaded and used for calculating the premium price for the given features of the individual.
Here is the link to the [Flask API](https://github.com/adgh82/insurance-premium-predictor-api)
Here is the link to the [Stream Lit app](https://github.com/adgh82/premium-calculation-ui)