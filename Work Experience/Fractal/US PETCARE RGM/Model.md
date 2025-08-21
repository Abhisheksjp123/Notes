So objective of model was to get elasticities for all the dependent variable and get R sq more than 75% and Mape< 5%
It was a timeseries model, that is we extracted following variables from the model to get time related attributes:
1. Seasonality
2. Time trend
3. first week of the month
4. sesonality
5. covid variables/ like covid week etc

Also modelling was done for each PPG for each retailer on its entire 5 years of data with the target variable volume sales or EQ LBS
Other features that we had for each PPG
1. ACV
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