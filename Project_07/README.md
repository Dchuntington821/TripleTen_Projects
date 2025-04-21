<b> Project Description </b>

The Company, 'Oily Giant' operates in three different regions and wants to drill 200 new wells with a budget of $100 million USD. Create a predictive model that helps determines which of the three regions contains the highest volume of oil reserves. Use bootstrapping and risk evaluation on the true values and predictions for each of the three regions in-order to determine which region will be the most profitable and contains the lowest risk. Three datasets were provided and R2 Score and RMSE were the primary metrics used in model evaluation. The risk of drilling in the chosen region needs to be below 5%.

<b> Data Cleaning </b>

1. Checked for missing values - none were present
2. Checked for duplicates - only a few were present and were dropped

<b> Data Pre-Processing </b>

1. Prepared the data by separating it into features and targets.
2. Split the data into training and testing sets.
3. Used Sklearn.StandardScaler() to scale numeric features

<b> Model Training </b>

1. Linear Regression - Sklearn

Three separate Linear Regression models were trained, one for each region. The metrics of these models allowed me to understand which of the models, and thus predictions were reliable. 
The results are as follows.

1. Region 1: r2 = 0.27 RMSE = 37.85 | Average Reserves/well =  92.7
2. Region 2: r2 = 0.99 RMSE = 00.89 | Average Reserves/well =  69.1
3. Region 3: r2 = 0.19 RMSE = 40.07 | Average Reserves/well =  94.8

<b> Profit Calculations </b>

In-order to better understand profitability and risk evaluation I needed to calculate the volume of oil each of the 200 wells would have to produce. The total volume of oil produce would need to exceed 22,000 units to be profitable.

I used this calculation paired with the predictions of the three models to determine which region would be the most profitable. Here are the results.

1. Region 1: The total volume of the 200 highest predicted wells for region 1 = 31070 | Total Profit = $139,815,000
2. Region 2: The total volume of the 200 highest predicted wells for region 2 = 27747 | Total Profit = $124,861,500
3. Region 3: The total volume of the 200 highest predicted wells for region 3 = 29695 | Total Profit = $133,627,500

<b> Bootstrapping and Risk Evaluation </b>

I performed bootstrapping on the true and predicted data to estimate the 95% confidence interval of expected profit for each region. For each region, I ran 1,000 simulations, selecting the top 200 oil wells based on model predictions. This allowed me to assess the average profit and the associated risk for each region. The risks for each region are as follows.

1. Region 1: Risk = 2.80% | Average Profit per well = $5,856,522
2. Region 2: Risk = 0.10% | Average Profit per well = $6,851,300
3. Region 3: Rish = 5.80% | Average Profit per well = $5,231,644

<b> Final Results </b>

My reccomendation to Oily Giant is to proceed with drilling the new wells in region 2 for three reasons.
1. The model for this region produced the most reliable results
2. It has the lowest risk evaluation of 0.10%, even in the lower quartile this region is profitable.
3. It has the highest average profit per well.

Not only is this the safest and most reliable region, but it is likely to be the most profitable. 






