This was the final project assigned to me by TripleTen. 

The primary goal of this project is to build a predictive model that accuractly predicts whether a client will churn while optimizing the AUC_ROC and Accuracy scores.

The general steps are as follows:

1. Clean and prepare data for EDA.
2. Perform EDA to determine relationships between features, what features could be engineered to improve a models accuracy, if there is an imbalance between classes present in the data.
3. Pre-processing: Engineer features, encode categorical data, scale numerical data, and split into training and testing sets
4. Model Creation: Build several types of models including a constant model to serve as a sanity check, classic models such as LogisticRegression, and finally, Gradient Boosted Models. Using GridSearchCV, tune hyperparameters and cross-validate.
5. Final Model Selection and Training: Out of the intial 6 models built, two returned the best scores: LightGBM Classifier and Sklearn GradientBoostingClassifier. These two models were then tuned much deeper allowing for an even better fitting model.
6. Prototype Model: The Model that performed best was the LightGBM Classifier returning an AUC_ROC score of 0.92 and an Accuracy Score of 0.88
