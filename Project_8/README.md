<b> Project Description </b> 

The mining company 'Zyfra' wants to create a prototype predictive model that accurately predicts the amount of gold recovered throughout different stages of extraction. Three datasets were provided that contain many different features that relate to purification processes, metal concentrations and gold recovered. sMape was the key evaluation with R2 Score and RMSE as additional metrics for evaluation.

<b> Data Cleaning </b>

1. Ensure data types are correct. - Some data types needed to be corrected
2. Check for and deal with any missing values. - I opted to simply drop the missing values as there were very few when compared to the size of the data sets.
3. Check for duplicates. - None Present

<b> Gold Recovery Calculation </b>

I needed to ensure that the gold recovery listed in the dataset was accurate. I was given the formula so all I did was write that formula into python, run the calculation and then take the mean absolute error of the result and the values already present in the dataset.

MAE = 9.46e-15 - An insignificant difference between my calculations and the data provided in the datasets

<b> Data Pre-Procesing </b>

This was quite a lengthy process as the datasets were continous and contained different portions of the full dataset. Some columns were not present in all the datasets and contained future data. Avoiding data-leakage was paramount in this task. These were the steps I took.

1. Verify how data has been split
2. Create a test set with the test target being 'final.output.recovery', will need to merge the test set with the full set on 'date'
3. Ensure that the test_feature data is the same as the test_target data
4. Split the data from the training set into a features and target set
5. Use the full data set to create a validation set that is the same size as the test set
6. Scale the feature sets

<b> EDA </b>

1. Create a dataframe that contains the average concentrations of metals au, ag, and pb for each stage of extraction.
2. Visualize the data frame
3. Visuzalize and compare differences in distributions for feed sizes from the primary and rougher stage of extration.
4. Create another dataframe that contains the sum of the concentrations of metals au, ag, and pb for each stage of extraction.
5. Visualize the data frame and analyze for outliers
6. Remove outliers if necessary

<b> Cross Validation </b>

Since I was predicting values across two different stages of extraction, all cross validation, model training and model evaluation needed to done twice.

1. Create a function that calculates sMAPE.
2. 5-fold cross validation on both a linear regression and a random forest regression model.

<b> Model Training and Selection </b>

I created a function that returns all of the metrics and trained two of each model to get the predictions of both stages of extraction. The models I trained are as follows.

1. Linear Regression - Sklearn
2. Random Forest Regression - Sklearn I ran the RF models through a loop to find the best hyper-parameters (depth, n_estimators) according to r2_Score and RMSE.

<b> Final Model Selection and Results </b>

The Random Forest Regressor was the best model with metrics as follows. 

1. First Stage
   * sMAPE = 13.3
   * R2 Score = 0.21
   * RMSE = 6.8

2. Second Stage
   * sMAPE = 17.6
   * R2 Score = 0.04
   * RMSE = 12.6

Final sMAPE = 14.4

<b> Final Conclusion </b>

Overall, I the set of features available to train with are simply missing important features that explain how they are related to the targets. This resulted in the models inability to capture the relationships between the different processes, inputs, and outputs of the extraction process in-order to produce reliable predictions. Having reliable data for the inputs of various metals along with feed sizes during different stages of the process would improve the results significantly.
     





