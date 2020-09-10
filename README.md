# Kaggle-Housing-Prices-Advanced
by Markus Müller

<a href='https://www.kaggle.com/c/house-prices-advanced-regression-techniques'>Link</a> to Kaggle competition 

## Goal of the competition
It is your job to predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable.

## Motivation
After learning data analytics and data science over 7 months now. I wanted to apply what I learned on a dataset that offers a lot of possibilities to implement creative feature engineering and advanced machine learning models to predict the sale price of a house.

## Data
- 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa.
- Data is split into training and test

## What did I do?
I first made a chapter notebook to explore the dataset, performed various preprocessing steps and visualized the features to select the ones I wanted to use in the final machine learning model. After I explored the dataset and tested the code I created a second notebook to only show the necessary steps and to focus more on the machine learning models. Till now I have implemented all the preprocessing and made the first predictions with the basic algorithms and a simple blended model


### List with things I did
- Visualized numeric and categorical features against the target (SalePrice) for feature selection
- Log transformation of SalePrice (skewed to the right)
- Imputed missing values, most of them were encoded to show a lack of a certain feature (so they were not really missing values). For categorical feature I mostlz imputed the mode and of numeric the mean or zero, when there were only 1 or 2 values missing.
- made sure that train and test set have the same features (which was a problem, but then I concatenate them and performed the preprocessing steps in both of them, keeping data leakage in mind).
- used LightGBM, XGBoost and Ridge and Lasso Rregression in cross validation to check for the best algorithem
- used LightGBM, XGBoost and Ridge in a simple blended model


## To-Do
- Feature engineering
- Hyperparameter tuning
- Stacking ml models
