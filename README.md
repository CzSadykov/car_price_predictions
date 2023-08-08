# Used car price prediction

**Problem Situation:** A supposed car dealership is developing an app to attract new customers. In it, you can quickly find out the market value of your car.

**Task:** to build a model to determine the cost, the RMSE metric should be **less than 2500 euros**.

**Criteria for evaluating work by the customer:**

- quality of prediction;
- prediction speed;
- studying time.

**Data:** historical. That is, the technical characteristics, equipment and prices of cars.

**Variables used:**

* ``DateCrawled`` — date of downloading the questionnaire from the database;
* ``VehicleType`` — car body type;
* ``RegistrationYear`` — year of vehicle registration;
* ``Gearbox`` — gear box type;
* ``Power`` - power (hp);
* ``Model`` — car model;
* ``Kilometer`` — mileage (km);
* ``RegistrationMonth`` — car registration month;
* ``FuelType`` — fuel type;
* ``Brand`` — car brand;
* ``Repaired`` - was the car under repair or not;
* ``DateCreated`` — date of creation of the questionnaire;
* ``NumberOfPictures`` - number of car photos;
* ``PostalCode`` — postal code of the owner of the profile (user);
* ``LastSeen`` is the date of the user's last activity.

**Target attribute:**

* ``Price`` - price in euro.

**Plan**:

So, let's start by importing the libraries and the models we use. In this problem, we will test predictions based on:

1) Linear regression;

2) Light GBM;

3) CatBoost.

## Conclusions

* For our predictions of used car prices we've compared 3 models: Linear Regression, Light GBM and Catboost. The initial threshold for passing the test was 2500 euro. 

* Based on RMSE, our top-2 models were Light GBM (RMSE: 1696) and Catboost (RMSE: 1584). However, Catboost took dramatically more time (+1 hour of training and +31 seconds of predicting) than Light GBM.

* So we've decided to **choose Light GBM with max depth of trees 11 and learning rate 0.3**. Its final RMSE on the test data is **1686.6 euro**. Just for comparison: RMSE of predictions based on average is 4492.8 euro. 

