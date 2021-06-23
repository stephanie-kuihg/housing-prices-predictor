# Predicting the Sale Price of properties in Ames, Iowa

### Objective of this Project
This project aims to inform potential home sellers and property investors in Ames of the top ten characteristics that will increase the value of their homes. Given a set of characteristics of their property, they will be able to get an estimation of their property value from the prediction model. 

### Background of Ames, Iowa
Ames is a city in Story County, Iowa, United States, located approximately 50km north of Des Moines in central Iowa. It is best known as the home of Iowa State University (ISU), with leading leading agriculture, design, engineering, and veterinary medicine colleges. <br/>
<br/>
In 2010, Ames was ranked ninth on [CNNMoney's "Best Places to Live"](https://money.cnn.com/magazines/moneymag/bplive/2010/snapshots/PL1901855.html) list! As Ames has been regularly named as one of the best places to live in, this project was established to analyse and predict house prices for potential home buyers relocating to Ames, or for those home sellers that would like to earn some money off selling their Ames properties.<br/>
<br/>
In 2019, Ames had a population of 66,258. Iowa State University was home to 33,391 students as of fall 2019, which make up approximately one half of the city's population. This high proportion of student population will have an effect on the property market with their lifestyle and amenities provided in the city. For example, Campustown is a high-density mixed-use neighborhood directly south of Iowa State University Central Campus that is home to many student apartments, nightlife venues, restaurants, and numerous other establishments, most of which are unique to Ames. <br/>
<br/>
Ames has a humid continential climate, with hot summers up to 39degC and cold winters down to -33degC. This extreme range of temperature throughout the year means that heating and airconditioning will be an important consideration to home buyers. ([From Wikipedia](https://en.wikipedia.org/wiki/Ames,_Iowa#2010_census))

### Project Description
This project uses the Ames Housing Dataset to create a regression model for predicting sale price of a given property with given set of features. As the dataset contains an extensive set of more than 80 features, the link to the [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) will be provided instead. 
#### Methods Used
Linear Regression
#### Tools
Python using Numpy, Pandas, Linear Regression, Matplotlib, Seaborn, Regularization, Standard Scaler
#### Needs of Project
Data Cleaning, EDA, Data Visualization, Modelling Techniques, Interpretation of Results to Non-Technical Audience

### Conclusions
#### A) The top ten characteristics that will increase the value of a property -   
1. Above Grade Living Area
2. Overall Quality - based on material and finish of the house
3. Year Built - based on original construction date
4. Overall Condition 
5. Neighborhood
6. Total Basement Area
7. Functionality
8. Lot Area
9. Having at least one fireplace
10. Exterior Quality

#### B) Renovations that home owners can consider doing to increase the value of their properties -  
1. Add a fireplace (If there were none before)
2. Repainting or minor facelift to the external of the property
3. Renovations to the kitchen

#### C) Usage of Prediction Model -
1. Upon submission to the [Kaggle Challenge](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/leaderboard), with the scoring based on RMSE, the lasso model yielded an RSME of 20580.
2. While the Kaggle challenge uses RMSE as the scoring system, it is not very interpretable as it depends on the scale of the target variable, which in this case it's sale price.
3. In this case of the RMSE being at about 20,000 - it means that the average difference from the actual sale price is about USD20,000 which is significant considering that the mean sale price is about USD180,000. Model still requires much fine-tuning before it can reach a production level algorithm.
3. Instead, we used R2 value to select a linear regression model for this project. Having a R2 value of 0.917 means that 91.7% of the variability in y is explained by the x-variables in our model.


### Further Recommendations
#### 1. Cleaning and EDA

Since this project serves as an exercise only, all the features were largely retained although they showed little to no correlation to the sale price. If this model were to be used for real life application, the features will have to be reduced to a reasonable amount such that data can be easily collected. <br/>
<br/>
Missing values for `Lot Frontage` was imputed with the mean value of the entire dataset. This could be improved by being more specific about the mean value being imputed, such as taking into consideration the neighborhood that the property is in, and taking the mean value of that particular neighborhood to be imputed instead.

#### 2. Feature Engineering

More features can be considered and mapped as ordinal variables rather than one hot encoding them as categorical variables, similar to that done for `Neighborhood` in version 1. Those features could be `Foundation`, `Roof Material`, `Masonry Veneer Type`, `Exterior 1` as they describe the building materials, and those materials can be graded by their quality.

#### 3. Modelling

While R2 value serves as an easily interpretable value, there may be too many variables in this dataset resulting it in being inaccurate for model selection as R2 will never decrease as you start adding more variables. Hence, an alternative assessment could be to use Adjusted R2 as the scoring system for the models instead. The current R2 value of 0.917 for a model to be applicable in real life sounds too good to be true!


