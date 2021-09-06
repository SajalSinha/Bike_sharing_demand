# Bike_sharing_demand
Currently Rental bikes are introduced in many urban cities for the enhancement
of mobility comfort. It is important to make the rental bike available and accessible
to the public at the right time as it lessens the waiting time. Eventually, providing
the city with a stable supply of rental bikes becomes a major concern. The crucial
part is the prediction of bike count required at each hour for the stable supply of
rental bikes. The main objective is to make a predictive model, which could help
them in predicting the bike demand proactively. This will help them in stable supply
of bike wherever needed.
The dataset contains weather information (Temperature, Humidity, Windspeed,
Visibility, Dew-point, Solar radiation, Snowfall, Rainfall), the number of bikes rented
per hour and date information. The Dataset has 15 columns and out of which 13 are
termed as Independent Columns. Our approach was to clean data, perform EDA and
gain insights, and train model. While doing EDA we made pair-plot of the variables
but as you might have seen it isn’t linear. We used RFE and VIF to do feature
selection. For 1st model we tried regression but got R-square value go 45% which
was far from good. Then we tried Decision tree regressor which gave a better result which was 0.87 and on further boosting and hyper parameter tuning our overall R-
square reached around 91% which was quite good.
