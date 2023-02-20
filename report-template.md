# Module 12 Credit Risk Analysis on outstanding loans

## Overview of the Analysis

### Purpose of the analysis.
Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. Analysis uses various techniques to train and evaluate models with imbalanced classes. Analysis uses a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

### Data 
1. The dataset contains a large amount of loan data, in which the column 'loan_status' has a value of either 0 or 1. A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting. 
2. Upon review the dataset displays imbalanced classes, which means that the existing classes in a dataset aren't equally represented. The pronounced imbalance between the two classes (“healhty” and “unhealthy” loans) can cause machine learning models to have a bias toward the larger class. The model will then excel at predicting loans that are healhty compared to those that are unhealhty. This is a problem if the goal is to detect unhealthy loans. In this dataset 97% of the loans are healthy and only 3% are marked unhealthy. 

### Machine Learning Process

1. Model: Choose a model appropriate for the Data
2. Fit: Let the model learn based on existing data
2. Predict: Make Predictions for new data
3. Evaluate the Model

### Methods Used
1. Model: Logistic Regression. We used Logistic regression because it can predit a binary outcome based on prior observations of a dataset. A logistic regression model predicts a dependent data variable by analyzing the relationship between one or more existing independent variables.

2. Resampling: Random Oversampling. To correct for the imbalanced data set I've used Random Oversampling. This creates more instances of a class label, usually for the smaller class. Resampling the data, increases the chance to create better-performing machine learning models. In random oversampling, the module randomly selects instances of the minority class and add them to the training set until there is a balance between the majority and minority classes.

## Results

![classification_report_compare.jpg](https://github.com/nielsdehaan1977/Fintech_Module12/blob/main/Images/classification_report_compare.jpg)

### Machine Learning Model 1 with original data:

**1. Dataset Balance**
* IMBALANCED: There were many more 'healthy loans' 97% in the data set than 'high-risk' loans 3%. (75036 healthy loans vs 2500 high-risk loans)

**2. Accuracy**
* VERY GOOD: Approximately 95.2% of the loans in the test data were accurately categorized by the model. But the model could have had high accuracy by simply predicting all healthy loans correctly due to the dataset imbalance.

**3. Precision:**
* VERY GOOD / GOOD: For 0 is 100% for 1 is 85% which is still good but might not be good enough for the purpose of this model, detecting high risk loans. 

* Healthy = 18663 / (18663 + 56) = 99.7%
* Unhealthy = 563 / (563 + 102) = 84.7%

**4. Recall**
* VERY GOOD / GOOD: For 0 is 99%, for 1 is 91% which looks good but might not be good enough for the purpose of this model. Model classified correclty 91% of the high risk loans, but still 56 loans were not correctly identified as high risk. 

* Healthy = (18663/(102+18663) = 99.4%
* Unhealthy = (563/(56+563) = 91%

**5. F1-Score**
* VERY GOOD/ GOOD: For 0 is 100%, for 1 is 88%. F1 score (the harmonic mean) is a single summary statistic for the precision and the recall. The model might have a high F1 score. But, that can prove deceptive, because the model might do a good job of predicting only our healthy loans. However, we’re interested in the unhealthy loans.

* F1 = 2 * (precision * recall) / (precision + recall)
* Healthy = 2 *((99.7% * 99.4%) / (99.7% + 99.4%)) = 99.7%
* Unhealthy = 2 * ((84.7% * 91%) / (84.7% + 91%)) = 87.7%



### Machine Learning Model 2 with Resampled Data:

**1. Dataset Balance**
* BALANCED: There are as many 'healthy loans' as 'high-risk' loans in the dataset, this is achieved by RandomOverSampler Module.

**2. Accuracy**
* VERY GOOD: Approximately 99.37% of the loans in the resampled compared to 95.2% in the original data. 

**3. Precision:**
* VERY GOOD / GOOD: For 0 is 100% for 1 is 84% which is slightly lower than in the original data. 

* Healthy = 18649 / (18649 + 4) = 99.98%
* Unhealthy = 615 / (615 + 116) = 84.1%

**4. Recall**
* VERY GOOD / VERY GOOD: For 0 is 99%, for 1 is 99%. Model with resampled data classified correclty 91% of the high risk loans, only 4 loans were not correctly identified as high risk. 

* Healthy = (18649/(116+18649) = 99.38%
* Unhealthy = (615/(4+615) = 99.35%

**5. F1-Score**
* VERY GOOD/ GOOD: For 0 is 100%, for 1 is 91%. Which is much higher than the approximate 88% based on the original data set. 

* F1 = 2 * (precision * recall) / (precision + recall)
* Healthy = 2 *((99.98% * 99.38%) / (99.98% + 99.37%)) = 99.68%
* Unhealthy = 2 * ((84.1% * 99.35%) / (84.1% + 99.35%)) = 91.09%

## Summary

All in, the model using resampled data was better at detecting unhealthy loans than what the model generated using the original, imbalanced dataset.
My Recommendation would be to use the model with resampled data as it performs much better on Recall, also the F1-Score is substantially better only precision was slightly less than in the model with original data. 
Recall improved significantly using resampled data, only 4 loans were not correctly indentified as high risk compared to 56 in the original data.




