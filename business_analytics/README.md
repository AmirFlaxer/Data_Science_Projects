1  Project description

You've been offered an internship in the analytical department at Yandex.Afisha. The first task is to help optimize marketing expenses. The data we have:

    Server logs with data on Yandex.Afisha visits from June 2017 through May 2018
    Dump file with all orders for the period
    Marketing expenses statistics

The tasks are:

    How people use the product
    When they start to buy
    How much money each customer brings
    When they pay off

1.1  Description of the data

The visits table (server logs with data on website visits):

    Uid - user's unique identifier
    Device - user's device
    Start Ts - session start date and time
    End Ts - session end date and time
    Source Id - identifier of the ad source the user came from

All dates in this table are in YYYY-MM-DD format.

The orders table (data on orders):

    Uid - unique identifier of the user making an order
    Buy Ts - order date and time
    Revenue - Yandex.Afisha's revenue from the order

The costs table (data on marketing expenses):

    source_id - ad source identifier
    dt - date
    costs - expenses on this ad source on this day


Table of Contents

    1  Project description
        1.1  Description of the data
    2  Open the data file and study the general information
        2.1  Download the data
        2.2  prepare it for analysis
            2.2.1  visits
            2.2.2  orders
            2.2.3  costs
    3  Make reports and calculate metrics
        3.1  Product
            3.1.1  How many people use it every day, week, and month
                3.1.1.1  DAU
                3.1.1.2  WAU
                3.1.1.3  MAU
                3.1.1.4  Conclusion
            3.1.2  How many sessions are there per day
            3.1.3  The length of each session
            3.1.4  How often do users come back
        3.2  Sales
            3.2.1  When do people start buying
            3.2.2  How many orders do they make during a given period of time
        3.3  What is the average purchase size
        3.4  How much money do they bring (LTV)
    4  Marketing
        4.1  How much money was spent? Overall/per source/over time
        4.2  How much did customer acquisition from each of the sources cost
        4.3  How much did customer acquisition from each of the sources cost
        4.4  How worthwhile where the investments? (ROI)
            4.4.1  ROI per cohort
            4.4.2  ROI per source
    5  conclusion
