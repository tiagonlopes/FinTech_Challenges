# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
  
  The main purpose of the analysis is to identify which future loans have a higher risk of default from the ones that are considered "healthy" loans. With that in mind we want to reduce as much as possible the number of loans we identify as healthy and turn-out faulty loans.
* Explain what financial information the data was on, and what you needed to predict.
  
  The main variable to predict is identify if the loan will default or not in the future. To reach it we have used previous data where we have included the:
    * Loan amount
    * Interest Rate
    * Borrower Income
    * Debt to Income Ratio
    * Number of Accounts
    * Derogatory Marks
    * Total Debt
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
  
  The variable we want to predict is: Loan Status. It is divided in a way theres is more than 75000 cases of "healthy" loans, compared with 2500 clients who have defaulted.
* Describe the stages of the machine learning process you went through as part of this analysis.
In order to train a model and create a overall machine learning process, we should apply a couple of sets like:
    1. Clean up and pre-processing the data, in order to make sure it is formated correctly. The major points to deal with are stated below:
        1. Verify if there are duplicates
        2. Assess and deal with NAs
        3. Assess ordinary variables and how to encode them
        4. Separate the Variables from the target, by creating 2 different datasets (Variables and Target)
    2. After both datasets are prepared (Variables and Target), we need to split the data in order to test and train the model. This step is usually done through train_test_split command.
    3. If needed, we should standardize the data. This step it is important to avoid biased towards certain variables given the scale compared with others. It is important to mention not all the times we will need to have this step.
    4. Define which model we are going to use and train it based on the training data.
    5. Assess the accuracy of the model, by looking for different metrics that can led us to conclude if the model answers the main question raised at the beginning.
    6. More common then not, the data is not balanced and we can try different methods to balance the data and then re-run steps 4 and 5 and compare the results.
    
  Despite not all the points are mandatory, it should be a good practice to look and understand the main problem and how the models answer them and how we can improve the results.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

    In this specific case we have utilized Logistic Regression and a reampling method based on Over-sample.

  Regarding Logistic Regression, the model does the selection based on applying the sigmoid function to the variables and then using a threshold to separate which of the categories. Moreover you can recover the probability of each set of variables belong to a specific class.

  In what concerns RandomOverSampler, it is a method that used the "under represented" data and generates more data points based on the distribution of the current data points. By doing so, it will increase the number of datapoints, reason why we call it OverSampling, because we increase the total number of points used on the model.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
    * Accuracy: 95.2%: it represents the number of times the model gives the correct prediction compared with the test data.
    * Precision: The precision of "high risk" is 85%. It means that out of all positive predictions just 85% were in reality positive. In this case, for the bank it represents a loss of an opportunity of provide a loan (cost of opportunity).
    * Recall: The recal of the first model is 91%. Based on the problem itself, this is one of the most important metrics, since the cost of predict a healthy loan and it lendes up in a default one has a high cost for the bank. The first model out of 100, 9 times, the model predicted that the would not default when it did.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
    * Accuracy: 99.4%. In the second model with the resampling of the data, the overall accuracy has increased. This in principle it is a good signal but given the context we will need to validate the recall.
    * Precision: 84% in the default loans.
    * Recall: 99%. It has increased compared with the previous model, therefore we should use it as better model.

## Summary

Given the current problem and the need to identify "1" - default loans - and the cost associated to a default loan, the main analysis of each model should be based on the recall for the loan status = 1. Thus, Model 2 performs better than one with 99% of recall compared with 91% on the first model. With that said, it is clear that we should use model 2.

