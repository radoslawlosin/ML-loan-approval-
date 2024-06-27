Machine learning algorithms in loan approval prediction.

1. Project goals

Prepare the dataset about Borrowers, cleansing data and understanding variables in dataset;

Divide the dataset for training data, validation data and test data;

Model training using supervised machine learning algorithms (Logistic regression and Random Forest algorithms);

Model validation and optimization; 

Analysis of the results of models - accuracy ;

Simulation of the Loan approval decision for new Applicant. 

Presenting the potential benefits and risks of the model results to financial institution.

First step: install packages (libraries) to environment;


2. Preparing of the dataset 

In this project the dataset from kaggle.com has been used: 

https://www.kaggle.com/datasets/krishnaraj30/finance-loan-approval-prediction-data/data?select=train.csv

This dataset contains 2 modules:

training (train.csv) that contains column with loan decision. We divide this module to 3 subset: training, validation and test.  

test (test.csv) that contains never seen before data of new applicants; 

Upload training data train.csv, and delete the Loan_ID column - it's unnecessary for loan decision:

Then check which columns contains NULL cells and how many:

The NULLs in cells are unwanted, so we must replace NULLs for values:

gender is "Female";

Married is Yes;

Dependents is 1;

Self_Employed is Yes;

LoanAmount is average;

Loan_Amount_Term is average;

Credit_History na 0 (no credit history).

Loan_Status from Yes/No for 1/0 (factor).

Add extra column (applicantquantity) with information about coapplicants: 

Then add an extra column with information about dependents (0 or 1). If Applicant have 0 dependents it will be 0, else 1.

The training module is now ready for further operation.


3. Training, validation and test subset.

The next step is to divide train.csv to 3 subset: training, validation and test. 

Set randomness set.seed(123);

Training subset (df_train) will contain 75 %  of data from train.csv;

The validation subset (df_valid) will be divided from df_train (33% of df_train) 

Test subset (df_test) will contain other 25 % of data from train.csv;

4. Visualization of dataset
   You will see it during the RStudio.  

5. Model training 

In this project two machine learning algorithms will be used:

- logistic regression - 3 variants;

- random forest.

One of the goals of model training is to check how each variable affect on loan status.


6. Model evaluation 

For each model compare the results with validation dataset. 

Check reliability of our models: compare results of validation dataset with training dataset using confusion matrix tool. 


7. Prediction for new applicants

The final result of this project is to automate the decision-making process for loan approval for new clients from test.csv dataset. 

First step is to prepare test.csv similarly to train.csv from the beginning. 

We make a prediction and save the result in the new column for logistic regression model and random forest model. 

End of file.
