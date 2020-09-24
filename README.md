# Kaggle-Housing-Prices-Advanced
by Markus Müller

- <a href='https://www.kaggle.com/c/house-prices-advanced-regression-techniques'>Link</a> to Kaggle competition 
- <a href='http://jse.amstat.org/v19n3/decock.pdf'>Link</a> to published paper on the dataset

## Goal of the competition
It is your job to predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable.

## Predictive score 
- mean absolute error on the train-test-split: $14657 (in general the sale price predictions are plus or minus 15000 dollars from the real price) - out of date
- Kaggle Score Histroy
  - 10.09.2020: 0.14469 (rmsle) with Ridge Regression and feature selection
  - 14.09.2020: 0.13608 (rmsle) with blended model (Ridge Regression, LGBM, CatBoost) and feature selection (top 45% of users)
  - 15.09.2020: 0.12521 (rmsle) with new blended model (Ridge Regression, LGBM, CatBoost, XGBoost) using nearly evey feature (top 25% of users)
  - 22.09.2020: 0.12131 (rmsle) with new blended model using Lasso and ElasticNet Regression each with tuned hyperparameters and transformation of skewed  numeric features (top 13% of users)
  - 24.09.2020: 0.12040 (rmsle) using stacking with the same algorithms as before (top 11% of users)


## Motivation
After learning data analytics and data science over 7 months now. I wanted to apply what I learned on a dataset that offers a lot of possibilities to implement creative feature engineering and advanced machine learning models to predict the sale price of a house.

## Data
- 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa.
- Data is split into training and test

## What did I do?
I first made a jupyter notebook to explore the dataset (predict_prices_exploratiion.ipynb), performed various preprocessing steps and visualized the features to select the ones I wanted to use in the final machine learning model. After I explored the dataset and tested the code I created a second notebook (predict_prices_model.ipynb) to only show the necessary steps and to focus more on the machine learning models. Till now I have implemented all the preprocessing and made the first predictions with the basic algorithms and a simple blended model


### List with things I did
- Visualized numeric and categorical features against the target (SalePrice) for feature selection
- Log transformation of SalePrice (skewed to the right)
- Imputed missing values, most of them were encoded to show a lack of a certain feature (so they were not really missing values). For categorical feature I mostly imputed the mode and of numeric the mean or zero, when there were only 1 or 2 values missing.
- Made sure that train and test set have the same features (which was a problem, but then I concatenate them and performed the preprocessing steps in both of them, keeping data leakage in mind).
- Used LightGBM, XGBoost and Ridge and Lasso Rregression in cross validation to check for the best algorithem
- Used LightGBM, XGBoost and Ridge in a simple blended model
- Used CatBoost and got a slightly higer score with the blended model
- Did hyperparameter tuning but didn't had any effect on the cross validation 


## To-Do
- Test different preprocessing steps
  - Transform skewed numeric features
- Learn more about the machine learning algorithms to do better hyperparameter tuning (use more advanced methods than just hardcoding verious values for each parameter)
- Feature engineering
- Stacking ml models


### Files
- predict_prices_exploration.ipynb: notebook to explore the dataset
- predict_prices_model.ipynb: notbook with all the preprocessing and basic models (out of date)
- Base_model: notebook with preprocessing and model evaluation
- Top_Model: most up to date notbook containing the highest performing ml-model
