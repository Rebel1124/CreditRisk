# Module 12: CreditRisk Report

# Overview of the Analysis

<br>

## Explain the purpose of the analysis.

For our analysis we were given lending data which which included features of the loan (X variables) as well as the loan status (y variable). The purpose of ur analysis was to use the loan features to make predictions on the loan status, i.e. whether the loan was high-risk or not. Making the analysis more compex was that the loan status was imbalanced, meaning that most of the data contained healthy with only a small percentage (approximately 3%) containing high-risk loans or loans in default.

<br>

## Explain what financial information the data was on, and what you needed to predict.

The lending data basically contained attributes (features) of loans as well the loan status (y variable). Essentially using a machine learning algorithm, where would use the loan features to train model to better predict wheter a loan would be high risk or not. 

<br>

## Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

From our anlysis we note that the variable to be predicted (loan status) had imbalanced data. With 75,036 loans being classified as healthy and only 2,500 reported as default or high risk. Naturally, given the imbalance, this would cause the model to be biased or influenced to predict more healthy loans than actually was. This is dangerous as it would cause the model to flag potentially high-risk loans as healthy.

<br>

## Describe the stages of the machine learning process you went through as part of this analysis.

For our analysis, after imorting the data we then performed the following steps:

* Split the data into train and test sets. By default 75% of data was used to train the model with the remaining 25% used to test themodel.
* We then used a logistic classifier model to fit the model on the training data.
* After training the model, we made predictions using the test set.
* Lastly we evaluated the model on the test set by looking at the balanced_ accuracy_score, confusion matrix and classification_report for imbalanced data.

Given that the data was indeed imbalanced, we then resampled the data by using the RandomOverSampler model to account for the imbalance in the data. After which we repeated the above steps again. 

<br>

## Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

As described above we used the Logistic Classfier model to make predictions. Since the variable to be predicted was binary, i.e. healthy or high-risk loans the logitic classifier model was an appropriate model to use. Additionally since we found the data to be imbalanced, we also used the Random Over Sample method to resample the data and account for the imbalance in the data.


<br>

## Results

## Machine Learning Model 1:
## Description of Model 1 Accuracy, Precision, and Recall scores.

* Balanced Accuracy Score: 0.9520479

* Precision (Healthy Loans): 1
* Precision (High-Risk-Loans): 0.85 

* Recall (Healthy Loans): 0.99
* Recall (High-Risk-Loans): 0.91

<br>

## Machine Learning Model 2:
## Description of Model 2 Accuracy, Precision, and Recall scores.

* Balanced Accuracy Score: 0.993678

* Precision (Healthy Loans): 1
* Precision (High-Risk-Loans): 0.84

* Recall (Healthy Loans): 0.99
* Recall (High-Risk-Loans): 0.99

<br>

## Summary
## Which one seems to perform best? How do you know it performs best?

On the surface Model 2 seems to perform better. The balanced accuracy score improved from 0.9520479 to 0.993678 and the recall for High-Risk-Loans also improved from 0.91 to 0.99. 
However when considering the precision scores, Model 1 produces a marginally better score 0f 0.85 (vs. 0.84 for Model 2). 

So although Model 2 seems to perform better overall, when considering the more important score (precision), it would appear that Model 1 does a better job. The precision score is more important since it would be more costly to flag high risk loans as healthy (i.e. false negative).

<br>

## Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

Yes! It more important to accurately predict '1's which represent high-risk-loans. It would be far more costly to flag a high-risk-loan as healthy and so in considering the problem we are trying to solve, the precision score becomes very important and so when looking at the model's performance I would think that this score (precision) would be the most import score to look at.

<br>

## If you do not recommend any of the models, please justify your reasoning.

Looking at both models precision scores, I would not recommend either model as I believe that both models does a poor job in accurately classifying high-risk-loans. I would go back-to the drawing board and look at perhaps using anoher machine learning model, such as random forests or support vector machine. If those models produce a better precision score then I would suggest looking at those models instead.