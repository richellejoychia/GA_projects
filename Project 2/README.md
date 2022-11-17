
# Project 2 - Helping realtors to predict sale prices in Ames 

## Introduction

All around the world, it is clear that house prices vary to a great extent. Sometimes, we do see that house prices differ even within the same area. How do we decide how much to sell or buy a property for? One common approach would be to ask a realtor to come up with a price. It sounds straightforward to put a price tag on the house, however, there is much more to it. As such, my team decided to conduct a survey among fellow colleagues to ask them about their experience with house prices. In general, we realized that realtors are spending way too much time trying to come up with a satisfactory number for their buyers/sellers. Moreover, they have to sieve through and consider various features.

My problem statement wouold then be how can we help fellow realtors effectively and efficiently predict the market value of houses in Ames, Iowa? 

As a data scientist and realtor at MyProperty, I have decided to use existing data to build an accurate model to predict sale prices. Put simply, realtors would be able to input the house features into the model and the ideal price would appear. For this project, I included a dataset that contains several variables, which can potentially be included in the model. For example, quality and quantity of physical attributes of residential homes sold between 2006-2010. Most of the variables contain information a typical home buyer would like to know about a property (e.g., square footage, number of bedrooms and bathrooms, size of lot). This link contains a description of the variables used in this dataset - http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

## Exploratory Data Analysis
Before analysing the datasets, it is important to do some data cleaning to identify and fix errors, duplicates, and irrelevant data from a raw database. In sum, I look at the correlation scores between housing features and sale price and the respective distributions 

## Data Cleaning, Preprocessing, and Feature Engineering

I did a couple of data cleaning and data wrangling to prepare the data for analysis and modeling.

There are a number of missing values in multiple columns. To sort out the missing values, I will split up the features into three separate categories based on the data dictionary: categorical variables where NA means no feature, numerical variables where NA means no feature, other variables where NA stands for missing values.

Next, I created new features based on existing ones in the data. The new data includes the total sq ft for the house, total number of bathrooms, age of the house, and whether the house is brand new. I believe these new features can help to reduce number of features while also making sense at the same time.

Then, I plotted a few correlation matrices to examine the relationship between the variables and predictor to examine:
- Potential multicollinearity between features
- High or low correlation between features and sale price 

Finally, I looked at a list of features with low variance in order to eliminate more features, which would help to reduce noise in the model.

## Modeling
These are the steps I took to prepare the features for modeling. 
- Train/test split: This step is used to estimate the performance of a prediction-based algorithim. This will allow me to compare my machine learning model results to the machine results. 
- Scaling: This step is crucial for the model as there are some features that may have different properties or do not follow a standard normal distribution. In other words, standardizing the features would help put everything on the same page.
- Instantiate our models
- Cross Validation: Estimating the skill of a machine learning model on unseen data to validate the performance of our model.


#### Summary of the train-test scores and RMSE 

After making the respective submissions on Kaggle, turns out our ElasticNet model returned with the best score in predicting house prices as well. However, like the table above, the scores did not differ significantly from other models. 

Since the scores do not differ too much from each other, I decided to use Lasso regression as the final model as it does help to cut down on the features, further reducing any potential noise. The  RMSE score on Kaggle is 24978.04.

## Conclusion and Recommendations
To conclude, I used the Lasso regression model as the final model to provide a more efficient and accurate service for realtors to predict the future sale prices of houses in Ames, Iowa. 
- In this model, 85 features were included in the model and 35 features were zeroed out by Lasso regression, which leaves a total of 50 features.

Here is the list of main features that were included: 
- Lot Frontage, Lot Area, Overall Cond, Year Remod/Add, Mas Vnr Area, Exter Cond, Bsmt Qual, Bsmt Exposure, BsmtFin SF 1, BsmtFin SF 2, Bsmt Unf SF, Low Qual Fin SF, Gr Liv Area, Bedroom AbvGr, Kitchen AbvGr, Fireplace Qu, Garage Finish, Garage Area, Wood Deck SF, Open Porch SF, Enclosed Porch, 3Ssn Porch, Screen Porch, Pool Area, Misc Val, Mo Sold, TotalBathroom, isNew, Exterior 1st, Exterior 2nd, Foundation, MS SubClass, Neighborhood. 
    
Moreover, I tried to include these 30 features into the main model, but the RMSE scores did not change significantly. As such, the final model used is still the Lasso regression model. 

## Recommendations

This model will help realtors make better recommendations to others. For example, sellers will be able to know which features to highlight when thinking about selling their house. Realtors will be able to create better proposals that allow them to sell property at current pricings and not undersell their property. Similarly, realtors can help prevent buyers from overpaying and perhaps look for better deals. 

More specifically, I would also recommend realtors to ask their clients to do invest in houses that have a higher above grade living area, be in a better neighborhood (specifically North Ridge or Stone Bridge), have a basement with higher ceilings, or bigger garage area. If the clients are buyers, they should also think about these features before buying so it can help them to earn more profits if they were to sell in the future. 


## Limitations and Future Considerations
These are the limitations and possible solutions related to the dataset:

- Data was collected between 2006-2010, which is more than a decade old. To build an even more accurate model, it would be better to gather new data so as to create a more effective model. This would take into account inflation over the past decade.

- The current model can only be applied to houses in Ames, Iowa, and not be generalized to other cities or states in the US. Perhaps collecting data from neighboring cities would be useful to see if the results hold.

These are the limitations and possible solutions related to the model: 

- The usage of other methods to eliminate features. Perhaps future work could examine other approaches that can also reduce dimentionality (e.g., principal compoenent analysis). 

- One of the cons of the current model is that it included outliers. I did attempt to exclude outliers from the model, but it did not increase the scores significantly. However, after collecting more data, it would be good to re-examine if outliers would influence the model. 
