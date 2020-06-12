# LendingClub Loan Default Prediction
*Build a loan default prediction model through machine learning and deep learning*
 
####  List of python libraries used
*pandas
*numpy
*seaborn
*matplotlib
*lightgbm
*sklearn

#### Files in the repository

*Jupyter notebook including all the code for this project

*loan.csv dataset

*Figures from the model evaluation results

## *Overview*

I. [Business Understanding](#Business-Understanding)<br>
II. [Data Understanding](#Data-Understanding)<br>
III. [Prepare Data](#Prepare-Data)<br>
IV. [Data Modeling](#Data-Modeling)<br>
V. [Evaluate the Results](#Evaluate-the-Results)<br>

## Business Understanding 

LendingClub is an American peer-to-peer lending company. It enables borrowers to create unsecured personal loans while investors can choose the loan to invest based on the information provided.

Borrowers pay the interest for the loan to settle their financial hardship. Investors make money from the interest. In the meanwhile, the platform charges startup fees from borrowers and service fees from investors.

One main concern of investors is whether borrowers would default on loans or not. If the default does happen, investors would lose their investment. In this project, I used the Light GBM and MLP to predict the borrowers' loan status and achieved an accuracy of 85%.

## Data Understanding

The dataset contains loan data for loans issued through 2007 to 2011, including the current loan status (Charged off, Fully Paid, etc.), loan amount, loan grade, loan purpose, and latest payment information. 

## Prepare Data

To build a prediction model based on this dataset, one important thing to notice is information leakage. As this dataset contains much up-to-date information related to the number of delinquency month and charge off collection fee etc, these features suggest a charge-off the loan. During the prepossessing stage, in addition to deal with missing values and categorical features, columns related to information leakage should also be removed for the model training.


## Data Modeling

Light GBM and MLP were trained on this dataset. The hyperparameters for Light GBM were chosen through 5-fold cross-validation.
The feature importance plot gave some of the influential features in the prediction.

![FI](https://github.com/yanhan-si/Lending-Club-Loan-Default-Prediction/blob/master/Light%20GBM_FI.png)


## Evaluate the Results

Our model achieved a high precion of 0.86 on the test set. The F1 score is 0.92.

When comparing the results from Light GBM with these from MLP, we can see that MLP did a better job on the training set with an 87 % training accuracy but the accuracy dropped by about 2 % on the testing set.

From the confusion matrix, we can see our classifier has high precision but low recall. This means the proportion of borrowers predicted to have good loan behaviors are indeed those who would fully pay the loan is high. But when the true label is charge-off, our classifier is not sensitive enough to notice that. This might be caused by the imbalanced class in the dataset. Actually, in this case, we do care more about precision as investors want to invest in those who are less likely to default.

![CM](https://github.com/yanhan-si/Lending-Club-Loan-Default-Prediction/blob/master/mlp_cm.png)


-------------------------------------------

### Reference:

1. https://www.kaggle.com/wendykan/lending-club-loan-data

2. https://medium.com/@syanhan96/lending-club-loan-default-and-interest-rate-analysis-47d395385876?sk=59ed3e1feff216e272c7f5d4dd51aa66

