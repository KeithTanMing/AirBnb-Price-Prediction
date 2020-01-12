# AirBnb-Price-Prediction

#### Refer to 'EDA & Modelling' notebook for data cleaning, analysis and modelling
#### Refer to 'Data Scrapping' notebook for data aquired from InsideAirBnb

## 1. Introduction

Airbnb is an American-based online marketplace for accomodation, primarly homestays, and tourism experiences. The company does not own the property, but acts as an online broker for individuals, earning commissions from each transaction. The company was incepted following the founder's rental of their home space, by placing an air mattress in their living room, effectively turning their apartment into a bed and breakfast. 

From a homeownder's perspective, deciding on a suitable price for a listing is an issue. There is a lack of clear and simple guidelines for setting the price - homeowners can only estimate based on historical price, and prices set by similar listings. While a new feature has been introduced (i.e. Smart Pricing; prices fluctuate automatically based on demand) by the company, homeowners still have to set an arbitary lower and upper bound for the price, and are oblivious to the factors that affect the movement of the prices - the lack of lucid information, and control over the input for factors that control the price, can be a source of frustration and lost income.

__Problem Statement:__ 
<br> Using New York as a case study, I would like to predict the daily price of listings, and in so doing, understand the factors that have significance influence on the price (e.g. location, quality of host)

__Approach:__
A year's worth of data (i.e. listings, reviews, calendar availability) was extracted from Inside Airbnb, an independent, non-commercial set of tools and data to explore how Airbnb is utilized in cities around the world. The data is then cleaned, analyzed, processed and ran through several machine learning models (e.g. Elastic Net, Random Forest Regressor, XGBoostRegressor).

## 2. Summary of Key Findings & Results

A total of 9 models were established. The best performing model came from __XGBoostRegressor__, at a regression prediction accuracy rate of __~80%__, and Root Mean Squared Error of __$2.08__.

![GridSearch](/Asset/Model_Gridsearch.png)

In descending order, the top 5 statistically significant features in predicting daily price are __'Occupancy Size'__, __'Neighbourhood'__, __'Cleaning Fee'__, __'Number of Bedrooms'__ and __'Minimum Nights'__.

While features such as occupancy size, neighbourhood and number of bedrooms are expected features, 'Cleaning Fee' came as a surprise. It is possible that cleaning fee is seen as an additional cost variable that is [Loss Aversion](https://corporatefinanceinstitute.com/resources/knowledge/trading-investing/loss-aversion/)

![FeatureImpt](/Asset/Feature_impt.png)

For further iterations, the model can be further improved by:
- Using PolynomialFeatures to explore interactions of features
- Translating non-english reviews to account for more accurate polarity scores
- Testing the robustness of the model on different geographical regions
