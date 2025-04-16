<b> Project Description </b>

The goal of this project was to build a classification model that predicts if a client will churn soon. The key Metric was F1 Score, I also used Auc_Roc score to understand how well the models differentiated between classes. One dataset was provided.

<b> Data Cleaning </b> 

1. Checked for duplicates (none were present)
2. Filled all missing values (many were present)


<b> EDA </b>

Completed a light EDA where I looked for correlations between different features and the target feature, 'Exited'. 

I also checked distributions between gender and features such as credit score, age, and salary in-order to determine feature importance.


<b> Data Pre-Processing </b>

1. Used pd.get_dummies() to one hot encode categorical features
2. Split the data into training, validation, and testing sets with sklearn.train_test_split()
3. Used Sklearn.StandardScaler() to scale all numeric features

<b> Model Training and Selection </b>

1. Random Forest Classifier - Sklearn
2. Logistiec Regression - Sklearn

Upon initial testing and tuning, it was clear that the Random Forest Classifier was the best fit for the data. 

<b> Final Model Improvements </b>

1. The initial metrics after tuning were as follows
  * F1 Score = 0.59
  * Auc_Roc = 0.72
    
2. In-order to improve the model further I upsampled the minority class. The results after this improvement were as follows.
   * F1 Score = 0.60
   * Auc_Roc = 0.74

3. Lastly, I adjusted the class weight parameter so that the positive class carried more weight.

<b> Final Results </b>

With these alterations the Random Forest Classifier improved by several points. 

F1 Score = 0.62
Auc_Roc = 0.76
    


