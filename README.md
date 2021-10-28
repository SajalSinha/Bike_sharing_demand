![00_2141_Bicycle-sharing_systems_-_Sweden](https://user-images.githubusercontent.com/79034119/139302598-39b94908-60dc-4753-bdd8-06c6ae7a5945.jpeg)




## Introduction

Seoul city provide rental bike to their people for certain amount for certain period
of time. But, the demand for bikes fluctuates with different conditions and so they aren’t
able to keep up with it. Our model aims at predicting Rented Bike demand at any time,
considering all conditions which will help them to manage the flow of bikes.
We will examine which machine leaning algorithms suits best with data along
with selection of features which have major impact in rented bike demand.

## 1. Problem Statement

Currently Rental bikes are introduced in many urban cities for the enhancement
of mobility comfort. It is important to make the rental bike available and accessible to
the public at the right time as it lessens the waiting time. Eventually, providing the city
with a stable supply of rental bikes becomes a major concern. The crucial part is the
prediction of bike count required at each hour for the stable supply of rental bikes.

The main objective is to make a predictive model, which could help them in pre-
dicting the bike demand proactively. This will help them in stable supply of bike wher-
ever needed.

The dataset contains weather information (Temperature, Humidity, Windspeed,
Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per
hour and date information.

## 1.1 Attribute Information:

• Date : year-month-day

• Rented Bike count - Count of bikes rented at each hour

• Hour - Hour of the day

• Temperature-Temperature in Celsius

• Humidity - %

• Windspeed - m/s

• Visibility - 10m

• Dew point temperature - Celsius

• Solar radiation - MJ/m2

• Rainfall - mm

• Snowfall - cm

• Seasons - Winter, Spring, Summer, Autumn

• Holiday - Holiday/No holiday

• Functional Day - NoFunc (Non Functional Hours), Fun(Functional hours)


Due to global warming, continuous pollution and depletion of sources of energy
Man countries have been focused oj using renewable energy which doesn’t harm
environment and can be reused as well. South Korea is one the country which has
adapted to it and their mostly used service is rented bike in Seoul. But in order to avoid
any difficulties such as waiting time it is necessary to have an estimate of future de-
mand.

Our goal here is to build model that can predict bike sharing demand considering
all the factors which have their effects.
## 1.2 Major Factors Affecting Bike Demand

A) Rainfall : People tend to use rented bike quite frequently due to the fact that
they can be easily rented from any place and can be dropped off any other place,
cheap enough to rent daily, but conditions like Rainfall affects its renting count a lot.

People don’t rent bike during rainy season. So we can say rainfall is negatively co-
related with rented bike count.

B) Snowfall : Similarly as rainfall, snowfall negatively affects rented bike count
as its hard to drive with snowy road.
C) Visibility : At times when one can’t see properly, its natural for them to avoid
driving, and this is what which affects the rented bike count. Although in Seoul,
case of these are quite low.

D) Temperature : It is seen that, people then to avoid renting bikes at low tem-
perature. Seoul is place with an average temperature of 27 to 32 degree Celsius.

So, when temperature become warm people tend to enjoy it which has an effect in
renting bikes as well.

E) Working Day or Not : Compared to an Off day, people rent bikes more on a
working day. Reason behind this is being the same I.e they can be easily rented
from any place and can be dropped off any other place, cheap enough to rent daily
F) Traffic : Even though this isn’y mentioned in data, traffic also support renting
bike count indirectly. If traffic is high or large people visiting nearby walk or rent a
bike for purpose.
## 2.Steps Involved

**A) Exploratory Data Analysis**
This analysis is important in order to gain useful insights within data and also wrt
dependent variable. In EDA variables are compared using plots and meaningful insights
are drawn. It gives us better idea of which feature behaves in which manner compared
to target variable.

**B) Data Cleaning**

Our Data contains some null values which might tend to disturb our accuracy
hence we dropped them at the beginning of our project to get better result.

**C) Encoding of Categorical Columns**
We used one Hot Coding to produce binary integers of 0 and 1 to encode our
categorical features because categorical features that are in string format cannot be
understood by machine and needs to be encoded.

**D) Feature Scaling**

Feature scaling is essential for machine learning algorithms that calculate dis-
tances between data. If not scale, the feature with a higher value range starts dominat-
ing when calculating distances.

**E) Fitting different Model**

At first we tried with basic linear regression, but soon realised we will need
much more complex model and so we then used Decision tree Regressor. Model is
then boosted and results are compared.

**F) SHAP Values**

We have applied SHAP value plots on the Decision Tree Regressor model to de-
termine the features that were most important while modelling and those who didn’t
supported as well.

## 3. Algorithms

**A) Regression**


![download (3)](https://user-images.githubusercontent.com/79034119/139302249-8dec2dd7-3119-446b-8341-5f8dec4704b9.png)



**B) Decision Tree Regressor**


![Screen-Shot-2019-05-17-at-00 09 26](https://user-images.githubusercontent.com/79034119/139302348-e426551b-daac-401c-b653-74a9a3147428.png)


**C) Gradient Boost**

![A-simple-example-of-visualizing-gradient-boosting](https://user-images.githubusercontent.com/79034119/139302453-8b2a2a56-0bde-4a43-87d6-de7476232c83.png)



## 4. Evaluation


1. R-squared (R2), which is the proportion of variation in the outcome that is

explained by the predictor variables. In multiple regression models, R2 corre-
sponds to the squared correlation between the observed outcome values and the

predicted values by the model. The Higher the R-squared, the better the model.
2. Root Mean Squared Error (RMSE), which measures the average error

performed by the model in predicting the outcome for an observation. Mathemat-
ically, the RMSE is the square root of the mean squared error (MSE), which is the

average squared difference between the observed actual outcome values and
the values predicted by the model. So, MSE = mean((observeds - predicteds)^2)
and RMSE = sqrt(MSE). The lower the RMSE, the better the model.

3. Residual Standard Error (RSE), also known as the model sigma, is a vari-
ant of the RMSE adjusted for the number of predictors in the model. The lower

the RSE, the better the model. In practice, the difference between RMSE and
RSE is very small, particularly for large multivariate data.

4. Mean Absolute Error (MAE), like the RMSE, the MAE measures the pre-
diction error. Mathematically, it is the average absolute difference between ob-
served and predicted outcomes, MAE = mean(abs(observeds - predicteds)). MAE

is less sensitive to outliers compared to RMSE.

## 5.Conclusion:

In project, after trying combinations of features with linear regression the model
underfit. It seemed obvious because data is spread too much. It didn't seem practical
to fit a line.

• With Decision tree we reached at the model R squared value of 0.86. We only
fitted with minimum number of leaf hyper-parameter. With default parameters it overfit-
ted and reached R-squared at 1 with train dataset but 0.86 with test.

• The Feature_importance is almost the same in both the tree based models.

Gradient boost fine-tunes with error of the prior trees this is why it gets better accura-
cies.

![download (4)](https://user-images.githubusercontent.com/79034119/139302967-a0f77469-5c29-4b25-b89c-1b6f719966e9.png)
