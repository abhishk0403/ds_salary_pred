# Data Science Salary Estimator:

## Project Overview

- I built a machine learning model to predict data science salaries
- This Model will help data scientists to negotiate their income when they get a job.
- The data cleaning process was carried out in Jupyter Notebook
- Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark
- Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model

# Code Used
Python Version: 3.9.13  
Packages: pandas, numpy, sklearn, matplotlib, seaborn

# Data Cleaning

I made the following changes and created the following variables:

Parsed numeric data out of salary
Made columns for employer provided salary and hourly wages
Removed rows without salary
Parsed rating out of company text
Made a new column for company state
Added a column for if the job was at the company’s headquarters
Transformed founded date into age of company
Made columns for if different skills were listed in the job description:
Python
R
Excel
AWS
Spark
Column for simplified job title and Seniority
Column for description length

# EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables.

![image](https://github.com/abhishk0403/ds_salary_pred/assets/140788396/52347816-8c9b-4efd-bcc5-eac39eebd314)  
![image](https://github.com/abhishk0403/ds_salary_pred/assets/140788396/11da6270-d61a-4226-9a77-1501455bc982)
![image](https://github.com/abhishk0403/ds_salary_pred/assets/140788396/1ed0e10c-a769-4cde-bdc5-4f0b72edc6e5)

# Model Building

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.
I tried three different models:
- Multiple Linear Regression – Baseline for the model
- Lasso Regression – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
- Random Forest – Again, with the sparsity associated with the data, I thought that this would be a good fit.

# Model performance
The Random Forest model far outperformed the other approaches on the test and validation sets.

Random Forest : MAE = 11.22  
Linear Regression: MAE = 18.86  
Ridge Regression: MAE = 19.67
