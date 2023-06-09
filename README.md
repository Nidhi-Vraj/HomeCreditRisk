# HomeCreditRisk
Created a Machine Learning model that predicts the loan eligibility
# Housecreditrisk
Created a Machine Learning model that predicts the loan eligibility
Home Credit Default Risk (HCDR)
The course project is based on the Home Credit Default Risk (HCDR) Kaggle Competition. The goal of this project is to predict whether or not
a client will repay a loan. In order to make sure that people who struggle to get loans due to insufficient or non-existent credit histories have a
positive loan experience, Home Credit makes use of a variety of alternative data--including telco and transactional information--to predict their
clients' repayment abilities.

Some of the challenges

# Dataset size
(688 meg uncompressed) with millions of rows of data
2.71 Gig of data uncompressed
Dealing with missing data
Imbalanced datasets
Summarizing transaction data
# Kaggle API setup
Kaggle is a Data Science Competition Platform which shares a lot of datasets. In the past, it was troublesome to submit your result as your
have to go through the console in your browser and drag your files there. Now you can interact with Kaggle via the command line. E.g.,
! kaggle competitions files home-credit-default-risk
It is quite easy to setup, it takes me less than 15 minutes to finish a submission.

# Back ground Home Credit Group
Many people struggle to get loans due to insufficient or non-existent credit histories. And, unfortunately, this population is often taken
advantage of by untrustworthy lenders.
# Home Credit Group
Home Credit strives to broaden financial inclusion for the unbanked population by providing a positive and safe borrowing experience. In
order to make sure this underserved population has a positive loan experience, Home Credit makes use of a variety of alternative data--
including telco and transactional information--to predict their clients' repayment abilities.
While Home Credit is currently using various statistical and machine learning methods to make these predictions, they're challenging
Kagglers to help them unlock the full potential of their data. Doing so will ensure that clients capable of repayment are not rejected and that
loans are given with a principal, maturity, and repayment calendar that will empower their clients to be successful.
# Background on the dataset
Home Credit is a non-banking financial institution, founded in 1997 in the Czech Republic.
The company operates in 14 countries (including United States, Russia, Kazahstan, Belarus, China, India) and focuses on lending primarily
to people with little or no credit history which will either not obtain loans or became victims of untrustworthly lenders.
Home Credit group has over 29 million customers, total assests of 21 billions Euro, over 160 millions loans, with the majority in Asia and and
almost half of them in China (as of 19-05-2018).
While Home Credit is currently using various statistical and machine learning methods to make these predictions, they're challenging
Kagglers to help them unlock the full potential of their data. Doing so will ensure that clients capable of repayment are not rejected and that
loans are given with a principal, maturity, and repayment calendar that will empower their clients to be successful.
Data files overview

# There are 7 different sources of data:
application_train/application_test: the main training and testing data with information about each loan application at Home Credit.
Every loan has its own row and is identified by the feature SK_ID_CURR. The training application data comes with the TARGET
indicating 0: the loan was repaid or 1: the loan was not repaid. The target variable defines if the client had payment difficulties
!pwd
!mkdir ~/.kaggle
!cp /root/shared/Downloads/kaggle.json ~/.kaggle
!chmod 600 ~/.kaggle/kaggle.json
! kaggle competitions files home-credit-default-risk
meaning he/she had late payment more than X days on at least one of the first Y installments of the loan. Such case is marked as 1
while other all other cases as 0.

#bureau:
data concerning client's previous credits from other financial institutions. Each previous credit has its own row in bureau, but one
loan in the application data can have multiple previous credits.
bureau_balance: monthly data about the previous credits in bureau. Each row is one month of a previous credit, and a single previous
credit can have multiple rows, one for each month of the credit length.

#revious_application: 
previous applications for loans at Home Credit of clients who have loans in the application data. Each current
loan in the application data can have multiple previous loans. Each previous application has one row and is identified by the feature
SK_ID_PREV.

# POS_CASH_BALANCE:
monthly data about previous point of sale or cash loans clients have had with Home Credit. Each row is one
month of a previous point of sale or cash loan, and a single previous loan can have many rows.
credit_card_balance: monthly data about previous credit cards clients have had with Home Credit. Each row is one month of a credit
card balance, and a single credit card can have many rows.
installments_payment: payment history for previous loans at Home Credit. There is one row for every made payment and one row for
every missed payment.

# ABSTRACT

HomeCredit uses Machine Learning Modeling to provide unsecured loans based on a user's
credit history, repayment behaviors, and other data. Credit history is a metric that explains a
user's reliability based on factors such as the user's average/minimum/maximum balance,
Bureau scores recorded, salary, and repayment practices. We used kaggle dataset to undertake
exploratory data analysis, develop machine learning pipelines, and evaluate models across
many evaluation metrics for a model to be deployed as part of this project. We used a deep
learning model in Phase-3. Using Pytorch, we created a binary classification Machine Learning
model in Python. We created a model, trained it, and evaluated it. We accomplished this by
constructing a neural network (NN) with one linear layer, a RELU layer, and a sigmoid function.
The linear NN had a high AUC of 0.609 and a 91% test accuracy.

# DATA AND TASK DESCRIPTION

. application_{train|test}.csv
This is the main table, broken into two files for Train (with TARGET) and Test (without
TARGET). Static data for all applications. One row represents one loan in our data
sample.
● POS_CASH_balance.csv
This dataset gives information about previous credits information such as contract
status, number of installments left to pay, DPD(days past due), etc. of the current
application. Monthly balance snapshots of previous POS (point of sales) and cash loans
that the applicant had with Home Credit.
● bureau.csv
All client's previous credits provided by other financial institutions were reported to the
Credit Bureau (for clients who have a loan in our sample). For every loan in our sample,
there are as many rows as the number of credits the client had in the Credit Bureau
before the application date.
● bureau_balance.csv
Monthly balances of previous credits in the Credit Bureau. This table has one row for
each month of history of every previous credit reported to the Credit Bureau.
● credit_card_balance.csv
Monthly balance snapshots of previous credit cards that the applicant has with Home
Credit.
● previous_application.csv
All previous applications for Home Credit loans of clients who have loans in our sample.
There is one row for each previous application related to loans in our data sample.
● installments_payments.csv
Repayment history for the previously disbursed credits in Home Credit related to the
loans in our sample. There is a) one row for every payment that was made plus b) one
row each for missed payment. One row is equivalent to one payment of one installment
OR one installment corresponding to one payment of one previous Home Credit credit
related to loans in our sample.

# TASK TO BE TACKLED

HomeCredit uses Machine Learning Modeling to provide unsecured loans based on the
consumers' historical credit history, repayment trends, and other data. Credit history is a metric
that explains a user's trustworthiness based on variables such as the user's
average/minimum/maximum balance, Bureau scores reported, salary, and repayment patterns.
We use kaggle datasets to undertake exploratory data analysis, develop machine learning
pipelines, and evaluate models across many evaluation metrics for a model to be deployed as
part of this project.
The goal of the HCDR initiative is to forecast the ability of the financially underserved
population to repay loans. This project is significant because both the lender and the borrower
require well-established predictions. Real-time Homecredit can show its consumers loan offers
with the highest amount and APR thanks to its ML pipelines, which acquire data from data
suppliers via APIs, run EDA, and fit it to the model to generate scores in microseconds. As a
result, risk analysis becomes extremely important in this situation, because NPA
(Non-Performing Asset) is expected to be less than 5% in order to run a profitable firm.


# IMPLEMENTING NEURAL NETWORK

According to,
https://machinelearningmastery.com/pytorch-tutorial-develop-deep-learning-models/,
the life-cycle of a PyTorch model has five steps. Prepare the data first. The second step
is to define the model. Finally, the model must be trained. Finally, assess the model
before making predictions.
● In section 3, we completed the first step. We'll define and train the model in
section 4.
● To begin, in the Figure 2 below, we show a loss prediction model on a TensorFlow
plot. In chart scaling, we ignored outliers. Smoothing was set to 0.6.
● The optimal loss function plot is shown below in Figure 2 for various numbers of
epochs.

# DEFINE THE MODEL

We define the layers of a model when we define it. To override the layers and propagate
input, we use the forward() function. We employ Linear, Conv2d, MaxPool2d, RELU,
Softmax, and Sigmoid extensively among the many available layers.
● A linear layer, for example, connects layers. They were convoluted by Conv2d,
then they were pooled by Maxpool2d.
● Activation functions include RELU, Softmax, and Sigmoid layers. We have codes
for these in our ipynb.

# EVALUATE THE MODEL
We may now evaluate the model on the test dataset because it has been fitted.
● With the predictions and actuals, we defined the evaluate model.
● We got a numpy array and rounded the numbers to class values. Then we stored it.
● The final step is to calculate accuracy.
● So we gathered the test dataset predictions, compared them to the expected values of
the test set predictions, and finally produced the performance metric. As previously said,
we have taken the reference from:
https://machinelearningmastery.com/pytorch-tutorial-develop-deep-learning-models/
● The ipynb file contains the codes.

# MODELING PIPELINES/ RESULTS AND DISCUSSIONS:

We used imputation to fill null values in the NAME TYPE SUITE column with "Other C" because
our null values were not trivial.
● In the columns containing the phrase AMT REQ CREDIT, we filled null values with 0.
● In the column containing the phrase CNT SOCIAL CIRCLE, we filled null values with 0.
● We used median to fill in the null values in the CNT FAM MEMBERS column.
● We used the median for the corresponding category to fill null values in the column AMT
GOODS PRICE.
● We removed one row that had the column DAYS LAST PHONE CHANGE set to null.
● We removed 12 records that had the column AMT ANNUITY set to null.
We evaluate the families of input attributes and count per family with bar and box plots for
more exploratory data analysis

# Hyperparameters and settings taken into account
For decision Making Tree, Lasso Regression, Ridge Regression, and Logistic Regression,
hyperparameter tweaking for grid search was performed.
● For a Decision Tree model, we experimented with different maximum depths and
sample splits.
● For Lasso Regression, we varied the alpha parameters and adjusted the penalty
weighting to the loss function.
● For Ridge Regression, we employed different alpha settings and varied the penalty to
loss function weighting.
● We utilized several C parameters for Logistic Regression and varied the penalty strength.
● We modified the amount of epochs, layers, and neurons per layer in PyTorch to improve
deep learning performance.

# LOSS FUNCTIONS:
As previously stated, we employ loss functions in the following manner.
● Loss functions include: The loss functions that we learned in class are used. That is, the
loss of binary cross-entropy. For binary classification, this loss function is utilized.

# RESULTS AND DISCUSSIONS:

We tried altering numerous parameters such as the number of epochs, the number of hidden
layers, and the number of neurons per layer as part of hyperparameter tuning for MLP
classification deep neural networks using Pytorch. Then we tallied the AUC and accuracy for
each iteration and discovered that there isn't much of a change, except for one combination
with three hidden layers, where AUC rose (74,35,8).
For binary classification, we used a Multilayer Perceptron Model.
The sigmoid activation function is used to forecast the probability of class 1 in the model. We
used stochastic gradient descent to optimize the model. We used the TensorBoard to show the
loss function. We also looked for Data Leakage by looking at Pre-Processing stages, Duplicates,
and testing and validating the model many times.
For the past month, we have had the results of the investigations. The deep learning model has
the best accuracy and AUC among the categorization models. The ridge regression model has
the lowest MSE and the highest AUC among the regression models. In phase three, we used
Pytorch to create the MLP Classification model, and we were able to achieve a better result. In
the future, we can use the hybrid Pytorch-FastAI technique to try a multi-task deep learning
model.
In order to summarize the project, We collected data in the first phase, performed EDA, and
developed a baseline model using logistic regression. We executed feature engineering and
tweaked the hyper parameters in the second step. Using Tensor board and binary classification,
we constructed a pytorch deep learning model in this step. We intend to provide a new
multi-task loss function in Pytorch as a stretch goal. The issue is that a multi-layer perceptron
regression model did not perform adequately.


# CONCLUSION

The goal of the HCDR initiative is to forecast the ability of the financially underserved
population to repay loans. This project is significant because both the lender and the borrower
require well-established predictions. Real-time Homecredit can show its consumers loan offers
with the highest amount and APR thanks to its ML pipelines, which acquire data from data
suppliers via APIs, run EDA, and fit it to the model to generate scores in microseconds. As a
result, risk analysis becomes extremely important in this situation, because NPA
(Non-Performing Asset) is expected to be less than 5% in order to run a profitable firm.
Credit history is a measure of a user's credibility that is calculated using characteristics
such as the user's average/minimum/maximum balance, Bureau scores reported, salary, and
repayment patterns that may be analyzed using the user's past timely defaults/repayments.
Other criteria such as location data, social media data, calling/SMS data, and so on are included
in alternate data. We would use the datasets given by kaggle for exploratory data analysis,
machine learning pipelines, and model evaluation across many evaluation metrics for a model
to be deployed as part of this project.
We estimated various models in phase 2, including classification and regression models.
Feature selection, data imputation, and hyperparameter tweaking. We began by performing
feature selection and imputation. The missing values of specified features were filled in. Then,
based on our past understanding, we opted to add relevant functionality. The hyperparameters
were then fine-tuned using GridSearchCV. We trained and assessed numerous models, including
Logistic Regression, Decision Tree Model, Lasso Regression, and Ridge Regression, to discover
the best one. In phase 2, classification models will not be able to outperform the baseline
model. The ridge regression model has the best performance among regression models.
In phase 3, we used PyTorch to design a deep learning model and created additional
models. The issues we had were that we couldn't increase the baseline model's test accuracy or
AUC using the feature selection and imputation stage. Unlike regression models, we were
unable to improve on the baseline classification model. To overcome these challenges, we
propose to create a multilayer model for loan default classification in PyTorch in phase 3. We'll
create and implement a new multitask loss function in Pytorch as a stretch goal. These were
submitted to Kaggle, and our results were published.
