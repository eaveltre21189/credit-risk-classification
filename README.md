# credit-risk-classification


## Overview of the Analysis

The purpose of this analysis was to create a model to predict the creditworthiness of potential borrowers. The dataset consisted of historical lending activity from a peer-to-peer lending company, including the loan amount and interest rate, as well as the borrower's income, debt-to-income ratio, number of accounts, total debt, and number of derogatory remarks. The objective of the model was to predict high-risk loans, or the likelihood of the borrower to default on the loan.

To conduct this analysis, I first reviewed the data, then identified the target variable (loan status). I then separated the data into training and test data. I defined a logistic regression model, fit the model with the training data, then ran a prediction of the results based on training. Then, I fit the model to the test data. To evaluate the performance of the model, I calculated the balanced accuracy score and confusion matrix, then generated a classification report. The model initially did well at predicting healthy loans, but wasn't quite good at predicting high-risk loans.

I speculated that the poor performance was due to the unbalanced data set - there were significantly more "healthy" loans in the training data than "high-risk" loans, which may have resulted in easier identification of healthy loans. To compensate for this limitation, I generated a new sample of data to train the model using a RandomOverSampler model. This ensured a balanced sample of healthy vs. high-risk loans when training the second iteration of the model. I repeated the above steps using the new resampled data to train the model, then fit the model to the test data again, and evaluated the results. I was then able to compare the two models to see if there was any improvement after using the second data sample.


## Results

* Machine Learning Model 1:
  * Balanced Accuracy Score: approx. 0.952
  * Precision:  1.00 for healthy loans; 0.85 for high-risk loans
  * Recall:  0.99 for healthy loans; 0.91 for high-risk loans

* Machine Learning Model 2:
  * Balanced Accuracy Score: approx. 0.994
  * Precision:  1.00 for healthy loans; 0.84 for high-risk loans
  * Recall:  0.99 for healthy loans; 0.99 for high-risk loans


## Summary

* Overall, the second model appears to perform better than the first; however, the improvement was not significant. The precision score for predicting high-risk loans actually decreased slightly (0.85 to 0.84), but the recall improved quite a bit (0.91 to 0.99).

* Both models did well at predicting healthy loans. However, the purpose of the model was to predict high-risk loans, and this is where the limitations were observed. Additional data could potentially be used to further improve the precision of the model at predicting whether a borrower might default on a loan. 
