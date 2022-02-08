1  Project description

Mined ore undergoes primary processing to get the ore mixture or rougher feed, which is the raw material for flotation (also known as the rougher process). After flotation, the material is sent to two-stage purification.

We have to train different models and evaluate them using cross-validation. Then to pick the best model and test it using the test sample.

1.1  The metric

sMAPE: similar to MAE, but is expressed in relative instead of absolute ones.

𝑠𝑀𝐴𝑃𝐸=1𝑁∑𝑖𝑁∣𝑦𝑖−𝑦̂ 𝑖∣(∣𝑦𝑖∣+∣𝑦̂ 𝑖∣)/2∗100%

1.2  The prediction

We need to predict two values:

    rougher concentrate recovery: rougher.output.recovery
    final concentrate recovery: final.output.recovery

𝐹𝑖𝑛𝑎𝑙 𝑠𝑀𝐴𝑃𝐸=25%∗𝑠𝑀𝐴𝑃𝐸(𝑟𝑜𝑢𝑔ℎ𝑒𝑟)+75%∗𝑠𝑀𝐴𝑃𝐸(𝑓𝑖𝑛𝑎𝑙)

1.3  Project instructions

    Prepare the data

    1.1. Open the files and look into the data.

    gold_recovery_train.csv

    gold_recovery_test.csv

    gold_recovery_full.csv

     1.2. Check that recovery is calculated correctly. Using the training set, calculate recovery for the rougher.output.recovery feature. Find the MAE between your calculations and the feature values. Provide findings.
     1.3. Analyze the features not available in the test set. What are these parameters? What is their type?
     1.4. Perform data preprocessing.

    Analyze the data

    2.1. Take note of how the concentrations of metals (Au, Ag, Pb) change depending on the purification stage.
    2.2. Compare the feed particle size distributions in the training set and in the test set. If the distributions vary significantly, the model evaluation will be incorrect.
    2.3. Consider the total concentrations of all substances at different stages: raw feed, rougher concentrate, and final concentrate. Do you notice any abnormal values in the total distribution? If you do, is it worth removing such values from both samples? Describe the findings and eliminate anomalies.

    Build the model

      3.1. Write a function to calculate the final sMAPE value.
      3.2. Train different models. Evaluate them using cross-validation. Pick the best model and test it using the test sample. Provide findings.

1.4  What is needed

    The model should predict the amount of gold recovered from gold ore. We have the data on extraction and purification. The model will help to optimize the prediction and eliminate unprofitable parameters.

    To predict the coefficient, we need to find the share of gold in the concentrate and the tail, both on rougher and finale.

