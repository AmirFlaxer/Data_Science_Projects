1  Project description

The telecom operator Interconnect would like to be able to forecast their churn of clients. If it's discovered that a user is planning to leave, they will be offered promotional codes and special plan options. Interconnect's marketing team has collected some of their clientele's personal data, including information about their plans and contracts.
1.1  Interconnect's services

Interconnect mainly provides two types of services:

    Landline communication. The telephone can be connected to several lines simultaneously
    Internet. The network can be set up via a telephone line (DSL, digital subscriber line) or through a fiber optic cable.

Some other services the company provides include:

    Internet security: antivirus software (DeviceProtection) and a malicious website blocker (OnlineSecurity)
    A dedicated technical support line (TechSupport)
    Cloud file storage and data backup (OnlineBackup)
    TV streaming (StreamingTV) and a movie directory (StreamingMovies)

The clients can choose either a monthly payment or sign a 1- or 2-year contract. They can use various payment methods and receive an electronic invoice after a transaction.
1.2  Data Description

The data consists of files obtained from different sources:

    contract.csv - contract information
    personal.csv - the client's personal data
    internet.csv - information about Internet services
    phone.csv - information about telephone services

In each file, the column customerID contains a unique code assigned to each client.

The contract information is valid as of February 1, 2020.
2  Work Plan

    read all the libraries
    load the data
    look at the data: all four data frame have one unique key to them. It is easier to merge all the data frames by the key to use the features of all the four files.
        join all the data frames to one using the customerID to merge them all
    analyze the type of the features:
        check the categorical features, how many option they have, is it numeric or strings. Are they mixed or the same type.
        pay attention to missing values when joining the data sets.
            if the missing value are targets, we cannot use it and delete the observation
            if the missing value are features, examine if they can be replace with option that relate to lack of this feature like 'No' or 0.
            replace the missing features with 'No'
        replace type 'object' to 'category'
        replace BeginDate from type 'object' type to datetime to be able to make manipulation on this feature.
    replace the datetime features with useful data that will help the model:
        the exact date of joining is less important than the period of the customer is with the company. Because the customers pay monthly, lets transform this data to calculate how many months the customers are customers for the company.
    calculate th target
        we need to know if the customer left or continue with the company. We do so by checking the EndDate column, if EndDate is not equal to 'No'(left the company), then it is Yes(continues).
    We now can remove the unnecessary columns:
        customerID
        BeginDate
        EndDate
    check for duplicates
    check for imbalance data. If problem with imbalance data exist, we can address it by imblearn library objects.
        we can try one of imblearn methods for oversampling (SMOTE) OR
        try one of imblearn combined methods for oversampling and undersampling (SMOTE + Tomek or SMOTE + ENN)
        we will have to check if addressing the imbalance problem giving better score.
    show the features distribution
    We will decide if we need to normalize the features, depend on the models we will choose. Some of the models doesn't need normalization.
    we will use encoding for all the categorical features for models that need it. We will use OHE Encoding on the features that are categorical
    before addressing the imbalance problem, we will divide the data to features and target
    and divide the data between train and test
    We will make to sets of train data:
        without change
        balance data

on the model

    run baseline model (Decision Tree)
    try cross validation on some models (random forest, Gradient Boosting, LightGBM and XGBoost)
    we will calculate the roc_auc_score
    then we will use the balanced data and run it all again.
    hopefully the ROC AUC score will be above 90%


