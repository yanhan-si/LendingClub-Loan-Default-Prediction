# Lending-Club-Loan-Default-Prediction
*Build a loan default prediction model through machine learning and deep learning*
 
## Business Understanding 

LendingClub is an American peer-to-peer lending company. It enables borrowers to create unsecured personal loans while investors can choose the loan to invest based on the information provided.

Borrowers pay the interest for the loan to settle their financial hardship. Investors make money from the interest. In the meanwhile, the platform charges startup fees from borrowers and service fees from investors.

One main concern of investors is whether borrowers would default on loans or not. If the default does happen, investors would lose their investment. In this project, I used the Light GBM and MLP to prediction the borrowers' loan status and achieved an accuracy of 86%.

## Data Understanding

The dataset contains loan data for loans issued through the 2007-2011, including the current loan status (Charged off, Fully Paid, etc.), loan amount, loan grade, loan purpose and latest payment information. 

## Prepare Data

To build a prediction model based on this dataset, one important thing to notice is information leakage. As this dataset contains much up-to-date information related to the number of delinquency month and charge off collection fee etc, these features suggest a charge-off the loan. During the prepossessing stage, in addition to deal with missing values and categorical features, columns related to information leakage should also be removed for the model training.


## Data Modeling

Light GBM and MLP were trained on this dataset. The hyperparameters for Light GBM were chosen through 5-fold cross validation.
The feature importance plot gave some of the influential features in the prediction.

![FI](https://github.com/yanhan-si/Lending-Club-Loan-Default-Prediction/blob/master/Light%20GBM_FI.png)


## Evaluate the Results

Our model achieved a high precion of 0.86 on the test set. The F1 score is 0.92.

![CM](https://github.com/yanhan-si/Lending-Club-Loan-Default-Prediction/blob/master/mlp_cm.png)


-------------------------------------------


## ***Table of Contents***

### *I. Exploratory Data Analysis*

### *II. Feature Engineering*

### *III. Model Fitting*

### *IV. Model Evaluation*

### *V. Conclusion*

https://medium.com/@syanhan96/lending-club-loan-default-and-interest-rate-analysis-47d395385876?sk=59ed3e1feff216e272c7f5d4dd51aa66

