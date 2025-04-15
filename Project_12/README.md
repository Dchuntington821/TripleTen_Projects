This was the final project assigned to me by TripleTen. 

The primary goal of this project is to build a predictive model that accuractly predicts whether a client will churn while optimizing the AUC_ROC and Accuracy scores. Four Datasets containing various customer information were provided.

The work plan for this project is as follows:

<b>Data Cleaning:</b>

While the data was very clean already, I had to verify two things.
1. There are no hidden missing values.
2. There are no duplicates, especially in the CustomerID columns per dataset
Data Analysis

<b> Exploratory Data Analysis: </b>

In this section I was looking for trends and patterns that related specifically to client churn rate. There were 6 primary areas of exploration. 

1. Total charges against billing type while taking into account the length of service.
2. Investigating the proportion of clients that also subscribe to services found in the internet column to see if that correlates with client longevity.
3. Whether any of the columns in the personal.csv (gender, senior citizen, partner, dependents) relate to length of service, total charges and monthly charges. There could be specific groups of people that tend towards longer or shorter service length or higher monthly charges for more premium subscriptions.
4. Investigating the paperless billing and payment method features to see if they hold any value in training a model.
5. Analyzing beginning and end dates to see how the length of service varies before discontinuing service.
6. Determine if there is a class imbalance.


<b> Data Pre-Processing: </b>

1. Merge the Data Using the Customer ID column after removing any features that I've determined to hold little to no value in model training.
2. Prepare the Target feature 'EndDate' to contain binary values, (no = 0) provided end date = 1.
3. Engineer new features.
4. Use OHE on categorical features.
5. Split the data into training, validation, and testing sets.
6. Scale all numeric features.


<b> Model Training and Selection: </b>

I created a constant model with DummyClassifier to serve as a sanity check, then I built 6 models while tuning and cross-validating with GridSearchCV

1. Sklearn Logistic Regression.
2. Sklearn Decision Tree Classifier
3. LightGBMClassifier with 'binary' objective type with 'gbdt' boosting.
4. Sklearn GradientBoostingClassifier, loss = 'log_loss'.
5. XGBoost XGBClassifier with 'binary:logistic' objective type and 'gblinear' booster.
6. CatBoost CatBoostClassifier with 'ordered' boosting type and 'logloss' function.

I tuned simpler versions of these models initially and then chose the two best performing models to tune deeply. Out of those two I chose the model that returns the best metrics to be the prototype.

<b> Results </b>

The results of the EDA can be found in the conculsion of the project notebook itself.

1. I added several new features including: start month, start year, total additional services per customer, total personal attributes per customer as there was a high degreee of correlation between attributes and service length. 
2. Final Model Selection and Training: Out of the intial 6 models built, two returned the best scores: LightGBM Classifier and Sklearn GradientBoostingClassifier. These two models were then tuned much deeper allowing for an even better fitting model.
3. Prototype Model: The Model that performed best was the LightGBM Classifier returning an AUC_ROC score of 0.92 and an Accuracy Score of 0.88 
