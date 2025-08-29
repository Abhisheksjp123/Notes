Objective: 
So objective of model was to get elasticities for all the dependent variable and get R sq more than 75% and Mape< 5%
# Data utilized
==Source data level==
Primary keys: Retailer + PPG
Time period: Saturday ending week date
* all the kpis for a week were aggregated at Saturday ending weekday for weekly timeseries analysis*

Data size:
Retailers = 23
PPGs = 300
Weeks = 5 years of data

Q. How were we evaluating the data as in I know we're using 5 years of data and using evaluation matrix of R SQ and MAPE and trying for R SQ>70% and MAPE<5%
What is the train set, what is the test set?
on how much weeks after we've our model are we predicting the data?

| PPG_ID | Week_Date  | Ln_EQ_Lbs_Sales (Actual) | Ln_Base_Price | Ln_TPR | Ln_Own_ACV | Disp_w/o_Feat_ACV | Stock_Piling | Covid_Dummy | Predicted_Ln_EQ_Lbs_Sales | Predicted_Actual_Sales | Base_Sales | Incremental_Sales | Incr_by_TPR | Incr_by_Display |
| ------ | ---------- | ------------------------ | ------------- | ------ | ---------- | ----------------- | ------------ | ----------- | ------------------------- | ---------------------- | ---------- | ----------------- | ----------- | --------------- |
| PPG001 | 2023-01-01 | 8.5                      | 2.1           | -0.1   | 4.2        | 0.05              | 0            | 0           | 8.48                      | 4811.2                 | 4500.0     | 311.2             | 180.5       | 90.7            |
| PPG001 | 2023-01-08 | 8.6                      | 2.15          | -0.05  | 4.21       | 0.03              | 0            | 0           | 8.59                      | 5389.7                 | 5000.0     | 389.7             | 100.2       | 150.8           |
| PPG001 | 2023-01-15 | 8.4                      | 2.12          | 0      | 4.19       | 0                 | 0            | 0           | 8.42                      | 4539.4                 | 4500.0     | 39.4              | 0.0         | 15.1            |
| PPG002 | 2023-01-01 | 7.9                      | 2.5           | -0.2   | 3.8        | 0.08              | 1            | 0           | 7.92                      | 2748.2                 | 2500.0     | 248.2             | 130.0       | 80.0            |
| PPG002 | 2023-01-08 | 7.8                      | 2.48          | -0.15  | 3.81       | 0.06              | 0            | 0           | 7.81                      | 2465.9                 | 2300.0     | 165.9             | 90.0        | 50.0            |







It was a timeseries model, that is we extracted following variables from the model to get time related attributes:
1. [[Seasonality variable]]
2. Time trend
3. first week of the month
4. covid variables/ like covid week etc
5. Holiday

Also modelling was done for each PPG for each retailer on its entire 5 years of data with the target variable volume sales or EQ LBS
Other features that we had for each PPG
1. ACV
	1. Disp_w/o_Feat_ACV
	2. Feat_w/o_Disp_ACV
	3. Feat_and_Disp_ACV
2. TDP
3. Price
4. Unit size
5. Shopper marketing variable
6. Feature promotion without display
7. Display promotion without Feature
8. Display and Feature together

We also Feature engineered like
1. Base price from AUP
2. OOS or Out of stock
3. Out of stock recovery
4. 5 top competitions ACV
5. 5 top competitions price

Also there was Media variable which I worked on to add
There were 5 variables in Media
tv_media, search_media, social_media, video_media, print_media
I used
GRP for TV and prints/circulation for print and impression/clicks for othere media verticle
Then I added adstock to that, I tried several different adstock to get highest correlation with the sales, and improved model performance
then I added saturation to that



Final output was this equation

 so we extracted 