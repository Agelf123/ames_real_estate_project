# Predicting Sale Prices for Ames Iowa Housing Dataset
By: Aryeh Gelfand(https://git.generalassemb.ly/aryehgelfand)

#### The Problem:
 I have been hired by the Ames Iowa Organization of Real Estate Agents in order to help them create better pricing models. Right now, they are using primitive comparative pricing metrics that aren't fit to the data available for the town. We have a dataset curated by Dr.Dean De Cock, a professor at Truman State University, that tracks 2051 real estate transactions that took place between 2006 and 2010 with 81 characteristics. We have been hired to create better price modeling for these real estate agents in order to help them add value to thier clients.
The plan is to use this data set to train a model that can accurately predict pricing, the metric we are using for success is Root Mean Squared Error, we will see how low we can get our it.
 - We will start by evaluating our features
 - Searching the dataframe for missing data
 - filling in missing data with proportional data points
 - generating new interaction terms
 - Training Linear Regression, LR with Ridge regularization and LASSO Regularization.
 - Then we will evaluate the models and choose the one with the lowest RMSE
 
 ####  Executive Summary

- Data Cleaning
This resulted in a large amount of null values. We also changed values proportional to the values that we had. Then we changed categorical values that were ordinal to integer values. We also created dummy columns.
 - EDA
We got the features with the top correlation coefficient and made interaction terms with them. Then made pair plots of these top performing features. We also engineered 12 new features based on categories likely to be related. Then we checked the correlation for these new values and scored them.
 - Modeling
We split the data into train and test values
Baseline
The baseline resulted in a model with a RMSE of 79K.
 - Linear regression
The training scores were significantly better than the testing scores and is therefore overfit. 
--- Training RMSE was 20882 
--- Testing RMSE was 23409

- Scale
--- Then we scaled the data to account for different measurementmetrics on the features
- Ridge
The regularization helped lower the error, we also used Ridge_CV to find the optimized Alpha at 10.
--- Training RMSE is 20996 
--- Testing RMSE 22118
 - LASSSO
The regularization didnt help as much, but still resulted in a better score than LR 
--- Training was 20881 
--- Testing was 22981
 - Model Selection
We selected the ridge model with an alpha of 10, because it resulted in the lowest RMSE
 - Model Evaluation
--- We used three graphs to evaluate the model.
--- A error distribution that proved that the erros have a normal distribution
--- A residual plot that showed a mean of 0
--- A Predicton vs True plot that showed homoskedasticity of errors

### Conclusions and Recommendations

 - When making models for the future, focus on subjective metrics like Overall Qual, Ext Quality, and Overal Cond, these have more of an effect than objective metrics like number of bedrooms or baths.
 - Also, the strategy of creating a lot of interaction columns and dummy variables and then using regularizatioin to scale it back has been succesfull and should be replicated.
 - The missing data strategy was also successful but has to be done in conjunction with the data dictionary.
 - Eliminate outliers in the target variable as these can cause the distribution to become skewed. This will result in in accurate predictions
 - 
 ### Data Dictionary

 - http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
  
 ### References
 - http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
 - http://jse.amstat.org/v19n3/decock.pdf








 
