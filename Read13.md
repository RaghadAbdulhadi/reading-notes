# Simple Linear Regression
Regression analysis explores the relationship between a quantitative response variable(dependent) and one or more explanatory variables(independent)

# How to run Linear regression in Python scikit-Learn
We can do linear regression using numpy, scipy, stats model and sckit learn.

**Scikit-learn** is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction.

*sklearn.linear_model* is a module which contains methods intended for regression in which the target value is expected to be a linear combination of the input variables.

### First Step:

    %matplotlib inline

    import numpy as np
    import pandas as pd
    import scipy.stats as stats
    import matplotlib.pyplot as plt
    from sklearn.datasets import anydataset

### Second Step:
Store the anydataset() in a variable

The variable is an object that is a dictionary

    To explore the keys in the dictionary
        
        varaiable.keys()

    To print the feature names of the data set
        
        print variable.feature_names

    To see the discription

        print variable.DESCR

    To convert boston.data into a pandas data frame

        varaible#2 = pd.DataFrame(varaible.data)
        varaible#2.head()

    To change the column names from numbers, with the feature names

        varaible#2.columns = varaible.feature_names
        varaible#2.head()

### Third Step: Linear Regression Model
Least squares method can be used as a way to estimate the coefficients.

1. Import linear regression from sci-kit learn module
    from sklearn.learn.linear_model import LinearRegression
2. Drop the column to assign it as X values 
    X = variable#2.drop("columnname, axis = 1)
3. Store linear regression object in a variable
    lm = LinearRegression()
    lm

To look inside the linear regression object, type LinearRegression, and the press <tab> key. This will give a list of functions available inside linear regression object.

**Important Functions:**

- lm.fit() -> fits a linear model

- lm.predict() -> Predict Y using the linear model with estimated coefficients

- lm.score() -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.

- We can also explore the functions inside lm object by pressing lm.<tab>

- .coef_ gives the coefficients and .intercept_ gives the estimated intercepts.

### Fitting a Linear Model

*fit_interceptbool, default=True*

If set to False, no intercept will be used in calculations.

*normalizebool, default=False*

This parameter is ignored when fit_intercept is set to False. If True, the regressors X will be normalized before regression by subtracting the mean and dividing by the l2-norm. If we wish to standardize, we should use StandardScaler before calling fit on an estimator with normalize=False.

### Predicting Prices
       lm.predict

### Training and validation data sets
In practice we wont implement linear regression on the entire data set, we will have to split the data sets into training and test data sets

#### How to do train-test split:
- divide the data sets randomly using the train_test_split function
-  build a linear regression model using train_test data sets
- calculate the mean squared error for training and test data

#### Residual Plots
Residual plots are a good way to visualize the errors in the data, data should be randomly scattered around line zero.
