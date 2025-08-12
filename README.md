# EDA and premium price prediction from an Insurance Dataset
## Contents
1. Introduction
2. Exploratory Data Analysis
3. Hypothesis Testing
4. Pre-Processing of data before modelling
5. Modelling
6. Comparison of model performance and conclusions
7. Further Studies
8. GitHub Repository and LinkedIn
9. Reference

## 1. Introduction
### 1.1 Objective

From the given dataset, identify the primary factors dominating the cost of the premium for the insurance of the individual. Identify critical insights which can help in designing tailor made proposals and incentivise individuals who are health concious and have lower probability of placing claims. Train a model to predict the insurance premiums for an individual given the features of the individual used for training the model. Make recommendations based on the analysis done on the dataset to ensure the insurance company is able to strike the optimum trade off between premium amount and probability of a claim.

### 1.2 Concepts Used

* Data Cleaning (including Null handling and Outlier detection using numpy, pandas, matplotlib and seaborn)
* EDA
* Hypothesis testing (using scipy library for statistical test)
* Data Preparation for modelling(using standard scaler from sklearn library)
* Predictions using regression models (using sklearn and xgboost library)

### 1.2 Dataset Overview

We will use the provided dataset which can be referred using the following github link -> Dataset. The dataset contains 986 datapoints which needs to be split across train and test data for the purpose of traning and assessing the  model performance. There are 11 features in the dataset and it is in csv format. The file size is 33KB.

### 1.2 Column Description
The dataset comprises the following 11 features: 
1. Age: Numeric, ranging from 18 to 66 years. 
2. Diabetes: Binary (0 or 1), where 1 indicates the presence of diabetes. 
3. BloodPressureProblems: Binary (0 or 1), indicating the presence of blood pressure-related issues. 
4. AnyTransplants: Binary (0 or 1), where 1 indicates the person has had a transplant. 
5. AnyChronicDiseases: Binary (0 or 1), indicating the presence of any chronic diseases. 
6. Height: Numeric, measured in centimeters, ranging from 145 cm to 188 cm. 
7. Weight: Numeric, measured in kilograms, ranging from 51 kg to 132 kg. 
8. KnownAllergies: Binary (0 or 1), where 1 indicates known allergies. 
9. HistoryOfCancerInFamily: Binary (0 or 1), indicating a family history of cancer. 
10. NumberOfMajorSurgeries: Numeric, counting the number of major surgeries, ranging from 0 to 3 surgeries. 
11. PremiumPrice: Numeric, representing the premium price in currency, ranging from 15,000 to 40,000.

Out of all these features, PremiumPrice is our target feature and rest of them are independent variables or features.
