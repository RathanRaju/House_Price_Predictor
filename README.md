# Bengaluru House Price Predictor using Machine Learning

* Built a model using sklearn and linear regression using Bengaluru House price data dataset from kaggle.com
* Firstly, performed data cleaning tasks which could remove unwanted features, outliers feature engineering, 
  dimensionality reduction, GridsearchCV for hyperparameter tuning, and k fold cross validation to before building the model. 
* Secondly, built the model using linear regression and created a python flask server that uses the saved model to serve http requests. 
* Third component is the website built in HTML, CSS and JavaScript that allows user to enter home square ft area, bedrooms etc and 
  it will call python flask server to retrieve the predicted price.
  

## Code and Resources Used 

**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, flask, json, pickle  
**For Web Framework Requirements:**  ```pip install -r requirements.txt```  
**Dataset:** https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data
