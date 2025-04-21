<b> Project Description </b> 

The company, Rusty Bargain, wants to add a feature to their app that allows customers to find out the estimated value for their vehicle by imputting features like year, model, miles etc. A prototype predictive model must be built that can accurately predict the value of a customers car while maintaning the lowest possible RMSE and a reasonable model training and prediction time as this model will be used in real-time. One dataset was provided.

<b> Data Cleaning </b>

1. Check for and handle all duplicates - A small amount of duplicates were dropped from the data.
2. Checking for and handling missing values.
   * This was a process as there were tens of thousands of missing values.
   * I created a function that would group the feature with missing values by a reliable feature like 'Model'. From there the function essentially took the mode value or category according to the grouping and created a new feature that contained the 'mode'. I then used this new feature to fill the missing values of the feature in question.
   * I used this function to fill all missing values.
   * Though I'm sure the results weren't perfect, they were certainly close and allowed me to retain a lot of useful data.
3. Lastly, I changed the data types where necessary.

<b> Data Pre-Processing </b>

1. Removed noisy features like postal code from the data.
2. Used One Hot Encoding on categorical features using pd.get_dummies()
3. Split the data into training, validation, and testing sets using Sklearn.train_test_split()
4. Scaled numeric features using Sklearn.StandardScaler()

<b> Cross Validation </b>

1. I created a scorer with the key metric 'RMSE' that I would use for each model using Sklearn.make_scorer()
2. I used Sklearn.cross_val_score() to complete a five fold cross validation on a Linear Regression Model, a Decision Tree Regressor, and a Random Forest Regressor.
3. This cross validation was a bit redundant as I used grid_search_cv() for each model, however; it was helpful to have a baseline, average rmse for each model.

<b> Model Training and Selection </b>

I used the python library 'time' to calculate the training and prediction time of each model as this would be a critical component of the prototype model. 
I created a Linear Regression Model to serve as a sanity check. RMSE = 3200, Training time = 1.95, Prediction Time = 0.04.
I trained each model using GridSearchCV() with 3 fold cross validation

The models I trained are as follows:
1. Decision Tree Regressor - Sklearn
2. Random Forest Regressor - Sklearn
3. LGBMRegressor - LightGBM
4. XGBRegressor - XGBoost
5. CatBoostRegressor - CatBoost

<b> Final Model Results </b>

The best model of the 5 was the XGBRegressor with metrics as follows:
RMSE = 1711
Training Time: 57 s
Prediction Time: 0.8 s



