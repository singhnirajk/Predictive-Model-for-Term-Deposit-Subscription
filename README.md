# Bank Marketing Project

This project analyzes bank marketing data to predict if a client will subscribe to a term deposit.

Dataset Link: https://archive.ics.uci.edu/dataset/222/bank+marketing

## Data

The data contains details on 45,211 marketing phone calls made to clients of a Portuguese bank. Each row represents a phone call, with the following features:

- **age**: age of the client
- **job**: type of job (management, technician, entrepreneur, etc.)
- **marital**: marital status (married, single, divorced) 
- **education**: education level (primary, secondary, tertiary, unknown)
- **default**: has credit in default? (binary: yes, no)
- **balance**: average yearly balance in Euros  
- **housing**: has housing loan? (binary: yes, no)
- **loan**: has personal loan? (binary: yes, no)
- **contact**: contact communication type (cellular, telephone, unknown)
- **day**: last contact day of the month (numeric: 1-31)
- **month**: last contact month of year (categorical: jan-dec)
- **duration**: last contact duration in seconds (numeric)
- **campaign**: number of contacts in this campaign (numeric) 
- **pdays**: days since previous contact (numeric)
- **previous**: number of previous contacts (numeric)
- **poutcome**: outcome of previous marketing campaign (categorical: unknown, failure, other, success)
- **y**: subscribed to term deposit? (binary: yes, no) - this is the target variable to predict.

## Exploratory Data Analysis

The data was explored visually to understand relationships between variables. Some findings:

- People aged 25-60 were most common in the data. 
- Married individuals were more common than single/divorced.
- Most contacts were made via cellular.
- Many people did not have loans or credit in default.
- Most calls occurred in May.
- Only ~12% subscribed to term deposits.

## Data Preprocessing

The data was preprocessed before modeling:

- Categorical variables were label encoded or one-hot encoded.
- Missing numeric values were imputed with the median.
- Data was split into train (80%) and test (20%) sets.

## Modeling

Several models were trained and evaluated:

- Logistic Regression
- Random Forest 
- Gradient Boosted Trees
- Neural Network
- SVM

The Random Forest model performed best with 100% accuracy on the test set.

## Feature Importance

The feature importances from the Random Forest model were:

1. Duration (28.8%)
2. Balance (10.5%) 
3. Day (9.4%)

This shows call duration, balance, and call day were the most predictive features.

## Propensity Scores

A logistic regression model was used to calculate propensity scores for the leads. A threshold of 0.5 was used to classify high vs. low value leads.

## Conclusion

The Random Forest model accurately predicted term deposit subscription on this dataset. Key takeaways:

- Focus marketing on leads with longer call durations, higher balances, and optimize for day of week.
- Use propensity scores to identify high-value leads for targeting.
- The model provides insights to improve marketing strategy.

Further improvements could be made by feature engineering and hyperparameter tuning.
