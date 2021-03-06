2  Load Data

The dataset is stored in the /datasets/faces/ folder, there you can find

    The final_files folder with 7.6k photos
    The labels.csv file with labels, with two columns: file_name and real_age

Given the fact that the number of image files is rather high, it is advisable to avoid reading them all at once, which would greatly consume computational resources. We recommend you build a generator with the ImageDataGenerator generator. This method was explained in Chapter 3, Lesson 7 of this course.

The label file can be loaded as an usual CSV file.
2.1  Project description

The supermarket chain Good Seed would like to explore whether Data Science can help them adhere to alcohol laws by making sure they do not sell alcohol to people underage. You are asked to conduct that evaluation, so as you set to work, keep the following in mind:

    The shops are equipped with cameras in the checkout area which are triggered when a person is buying alcohol
    Computer vision methods can be used to determine age of a person from a photo
    The task then is to build and evaluate a model for verifying people's age


Table of Contents

    1  Initialization
    2  Load Data
        2.1  Project description
    3  EDA
        3.1  Showing picture sample
        3.2  Findings
    4  Modelling
        4.1  Prepare the Script to Run on the GPU Platform
        4.2  Output
    5  Conclusions
