# Bengaluru House Price Predictor using Machine Learning

* Built a model using sklearn and linear regression using Bengaluru House price data dataset from kaggle.com
* Firstly, performed data cleaning tasks which could remove unwanted features, outliers feature engineering, 
  dimensionality reduction, GridsearchCV for hyperparameter tuning, and k fold cross validation to before building the model. 
* Secondly, built the model using linear regression and created a python flask server that uses the saved model to serve http requests. 
* Third component is the website built in HTML, CSS and JavaScript that allows user to enter home square ft area, bedrooms etc and 
  it will call python flask server to retrieve the predicted price.
  

## Code and Resources Used 

**Python Version:** 3.7  
**Packages:** Numpy and Pandas for data cleaning, Sklearn for model building, 
              Matplotlib for data visualization, Jupyter notebook, visual studio code and pycharm as IDE,
              Python flask for http server, HTML/CSS/Javascript for UI. 
**For Web Framework Requirements:**  ```pip install -r requirements.txt```  
**Dataset:** https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data


## Data Cleaning

After loading the data, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

*	Drop features that are not required to build our model 
*	Added new feature(integer) for BHK (Bedrooms Hall Kitchen), the size column has a different type of Annotation like 4 Bedroom instead of BHK. 
  So, I added another column called BHK and assigning the value of the number of rooms to it.
*	In our dataset, there were some rows in total_sqft there has been a range of values. We need to convert this range of values into float and then take the     
  average between the min and max value to return a single value
*	Dropping some rows which contains Sq. Meter in total sqft.
*	Applying Dimensionality Reduction to reduce the location having less than 10 data points to be tagged as "other" location
*	Removing the Outliers Using Business Logic
*	Using One Hot Encoding For Locations

## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried three different models and evaluated them using K Fold cross validation. 

*	**Linear Regression** – Baseline for the model
*	**Lasso** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
*	**Decision Tree** – Again, with the sparsity associated with the data, I thought that this would be a good fit. 

## Model performance
Used GridSearchCV to identify the best model
The Linear Regression far outperformed the other approaches on the test and validation sets. 
*	**Linear Regression** – 84.77%
*	**Lasso** – 72.67%
*	**Decision Tree** - 71.51%

## Productionization 
In this step, I built a flask API endpoint that was hosted on a local webserver and also built the front-end of the the website using HTML, CSS and JavaScript. The API endpoint takes in a request with a list of values (Area (Square Feet), BHK, Bath, Location) and returns an Estimated Price. 


![alt text](https://github.com/RathanRaju/House_Price_Predictor/blob/master/Home_page.JPG "Client Side")
