3  Project description

Beta Bank customers are leaving: little by little, chipping away every month. The bankers figured out it’s cheaper to save the existing customers rather than to attract new ones. We need to predict whether a customer will leave the bank soon. We have the data on clients’ past behavior and termination of contracts with the bank.

Our mission: Build a model with the maximum possible F1 score. To pass the project, you need an F1 score of at least 0.59. Check the F1 for the test set.

Additionally, measure the AUC-ROC metric and compare it with the F1.

Type of problem Classification
3.1  Data description

Features

    RowNumber -data string index
    CustomerId - unique customer identifier
    Surname - surname
    CreditScore - credit score
    Geography - country of residence
    Gender - gender
    Age - age
    Tenure - period of maturation for a customer’s fixed deposit (years)
    Balance - account balance
    NumOfProducts - number of banking products used by the customer
    HasCrCard - customer has a credit card
    IsActiveMember - customer’s activeness
    EstimatedSalary - estimated salary

Target

    Exited - сustomer has left

