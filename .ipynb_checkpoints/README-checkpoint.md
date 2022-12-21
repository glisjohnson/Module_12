# Module_12

## Overview of the Analysis

* The purpose of this analysis is to test a Logistic Regression Model with data to accurately determine the creditworthiness of a borrower. Then we resample the data and run the new data through the model again. This creates a new model, since it was trained with new data. We will run tests and at the end, determine the viability of either of the models.

* The financial information was on data that goes into the decision making process at a bank of if you get a loan or not. What we needed to predict was whether the borrower should get a loan or not, using the model to return a "0" or "1" for healthy loan or high-risk loan, respectively.

* One variable we were trying to predict was value_counts, which as we used it, showed us the totals of all the outputs in the variable (y). These outputs were prodominately 0 which corresponded with an approval for a loan, and the rest were 1 meaning risky. Another variable we were trying to predict was funnily enough, predict(). We used predict() to test the model's accuracy by having it output "0" or "1" given all the information of our dataset, except the actual loan status.

* After reading in the data, we first split off the "loan_status" column as its own dataframe in order to allow for our model to try. Then from sklearn, we used the function "train_test_split" on our two dataframes to randomly split up the datatables in half (it is actually 70/30). This is so we can feed the model half the data to train it and then the other half to test it. 

* A method we used was "LogisticRegression", which created the model we needed to feed data through. Also, "fit_resample" was used in order to shuffle our data and have essentially new data to feed through the model. 

## Results

* Machine Learning Model 1:
  * The balanced accuracy score of Machine Learning Model 1 (MLM1) is 0.9442676901753825. The balanced accuracy score is equal to the average of the recall scores.
  * The precision scores for MLM1 were 1.00 for "0" and 0.87 for "1". Precision is equal to True Positives / (True Positives + False Positives) which means the MLM predicted all of the 0's correctly but got 13% of the 1's wrong. 
  * The recall scores for MLM1 were 1.00 and 0.89, respectively. Recall is equal to True Positives / (True Positives + False Negatives) which means for the 0's, the MLM was perfect but for the 1's, it predicted 11% of the negatives incorrectly. 



* Machine Learning Model 2:
  * The balanced accuracy score of Machine Learning Model 2 (MLM2) is 0.9959744975744975. This score is very close to 1, making it very accurate. If it was equal to 1.00, I would assume the MLM is not reading the data correctly. 
  * The precision scores for MLM2 were: 0:1.00; 1:0.87. This means the model did perfectly determining the status of all healthy loans while mistaking 13% of unhealthy loans for healthy loans. 
  * The recall scores for MLM2 were: 0:1.00; 1:1.00. We know from the balanced accuracy score that these values are rounded up, and not actually 100%'s. So this means, for determining both healthy and unhealthy loans, MLM2 got only a couple wrong, max.

## Summary

* It seems like that Machine Learning Model 2 performs the best. I know it performs the best by comparing the important statistics between both Machine Learning Models. Both Machine Learning Models had the same precision scores, however Machine Learning Model 2 had much higher recall scores, making the balanced accuracy score in favor of Model 2 as well. 

* Performance does not depend on the problem we are trying to solve. For example, it is more important to predict the 1's rather than 0's because the 1's are the high-risk cases. You could make a model's default mode be to just check all 0's and you would be mainly correct since most borrowers are 0's. However, when working in high-level financial institutions like a bank or credit union, you need precise numbers. One zero in the wrong place and everything could be ruined. With that being said, I would not recommend the use of either of the Machine Learning Models because both of the models are mistaking 13% of unhealthy loans for healthy loans, aka if the bank used either model, they would be loaning money to high-risk entities and probably lose money. 