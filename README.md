# Credit_Risk_Classification

## Overview of the Analysis

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this analysis, the logistic regression model from Python SKLearn library is used to build a supervised machine learning model, with a set of lending data that has imbalanced classes, ie. significantly more healthy loans than high-risk loans. The dataset used in this analysis is the historical lending activity from a peer-to-peer lending services company. The model built through this analysis can be used to predict if a loan to be approved in the future is likely to be healthy, or high-risk.

The dataset used in this analysis has the following information: Borrower Income, Debt to Income Ration, Number of Accounts, Number of Derogatory Marks, Total Debt, and the loan status, whether the loan is already classified as healty, or high-risk.

In the dataset, there are a total of 77,536 loans, of which 75,036 loans are classified as healthy ('0'), and 2,500 loans are classified as high-risk ('1').

The machine learning process involves the following:

1. Read the dataset, which is in a flat file named 'lending_data.csv' into a Pandas dataframe.

2. Assign the loan status column to as the 'target', or 'y', array. Assign the rest of the columns to the 'features', or 'X', array.

3. Split the dataset into two sections, one for training the model, and one for testing the model. The split is 75% to 25%, ie 58,152 (train) to 19,384 (test).

4. Instantiate a logistic regression model, fit (ie. train) the model using the training data, then use the model (Model 1) to predict the loan status using the test data.

5. Since the dataset is highly unbalanced in number of healthy versus high-risk loans, the original training data is run through a Random Over Sampler algorithm (from Python imblearn library) to produce a balanced dataset with the same number of healthy and high risk loans. The logistics regression machine learning model is then built on the over-sampled dataset. The original set of test data is then run through the new model (Model 2).


## Results

The following are the results of the logistic regression machine learning model using the original imbalanced dataset and the over-sampled dataset:

* Model 1: Logistic Regresssion with original imbalanced training dataset:
  * The overall accuracy was 99%, precision (correct predictions) using the test data for healthy loans versus high-risk loans were 100% versus 85%, and the recall ('predictions' using the training data) was 99% for the healthy loans versus 91% for the high-risk loans.


* Model 2: Logistic Regresssion with over-sampled 'balanced' training dataset:
  * The overall accuracy was 99%, precision (correct predictions) using the test data for healthy loans versus high-risk loans were 100% versus 84%, and the recall ('predictions' using the training data) was 99% for both training and test data.


## Summary

The above results showed that the logistic regresssion model using over-sampling provides a better overall result. The f1 score for the prediction of high-risk loans (91%), a more important measure in this case, is 3% higher than using logistics regression with the original dataset.

It is recommended that logistic regresssion model using over-sampling be used when predicting if a loan is high risk.


---

## Technologies

This analysis is written for use with Jupyter Lab. It uses the following packages:. It uses the following packages:

* [Pandas](https://github.com/pandas-dev/pandas)
* [sklearn](https://scikit-learn.org)
* [imblearn](https://imbalanced-learn.org)


---

## Usage

In Windows GitBash or Mac Terminal app, enter "Jupyter Lab". Then open and run "credit_risk_resampling.ipynb".

The "lending_data.csv" file must be in a sub-folder "Resources".


---

## Contributors

This application is written by James Tan, with code snippets provided UBC Extension.

---

## License

MIT.

