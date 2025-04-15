<b> Project Description </b>

The Film Junky Union, is developing a system for filtering and categorizing movie reviews. The main task is to train a model to automatically detect negative reviews by training a build a model that classifies positive and negative reviews. It will need to have an F1 score of at least 0.85. The data set provided contained IMBD movie reviews with polarity labelling.

<b> Data Cleaning </b>

1. Handle all missing and duplicated values.

<b> EDA </b>

1. Investigate balance between positive and negative classes.
2. Understand how moview review classification has changed over time.

<b> Pre-Processing </b>

1. Normalize the text
2. Split data into training and testing sets.
3. Tokenize and lemmatize with spacy.
4. Complete TF-IDF Transformations with TfidVectorizer.
5. Create an evaluation function that can be used on each model.

<b> Model Training and Selection </b>

Built 5 models and an additional constant model to serve as a sanity check, all models were tuned and cross-validated with Sklearn.GridSearchCV

1. Logistic Regression - Sklearn
2. Decision Tree Classifier - Sklearn
3. LGBMClassifier - LightGBM
4. Gradient Boosting Classifier - Sklearn
5. XGBClassifier - XGBoost

After initial training and hyperparameter tuning, I used these models to classify additional reviews not present in the dataset. From there, I chose the model that I believed best fit the task.

<b> Results: </b>

1. Logistic Regression - F1 Score = 0.878. Correctly classified 6 of 8 reviews.
2. Decision Tree Classifier - F1 Score = 0.757. Correctly classified 3 of 8 reviews
3. LGBMClassifier - F1 Score = 0.870. Correctly classified 6 of 8 reviews.
4. Gradient Boosting Classifier - F1 score = 0.862. Correctly classified 7 of 8 reviews.
5. XGBClassifier - F1 Score = 0.81. Correctly classified 7 of 8 reviews.

<b> Final Model Selection </b>

I believe the LightGBM Gradient Boosting Classifier is the best model for the data. Despite it having lower f1 score than two of the models, it correctly identified 7 of 8 reviews and I believe it has potential to exceed the scores of the Logistic Regression and the GBDT models if tuned deeper. The hyperparameter tuning I ran on this model was preliminary and it quickly achieved an F1 score of 0.86, I think that with further tuning the F1 score could exceed logistic regression. 


   

