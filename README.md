# Alphabet Soup Charity Neural Network Analysis

## Overview

This project uses machine learning models to predict the success of ventures paid by the made up company "Alphabet Soup". The goal was to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup and which are too high risk to ensure the foundations money is being used effectively.

## Resources

- Data Source: a dataset containing 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

EIN and NAME: Identification columns
APPLICATION_TYPE: Alphabet Soup application type
AFFILIATION: Affiliated sector of industry
CLASSIFICATION: Government organization classification
USE_CASE: Use case for funding
ORGANIZATION: Organization type
STATUS: Active status
INCOME_AMT: Income classification
SPECIAL_CONSIDERATIONS: Special consideration for application
ASK_AMT: Funding amount requested
IS_SUCCESSFUL: Was the money used effectively

### This repository employs the following Python libraries:

- TensorFlow (neural networks)
- Pandas
- Sk-learn (machine learning models and preprocessing)


## Resuls and Analysis

The project was divided into 3 parts: 

### 1) Preprocessing Data for a Neural Network Model

- The target variable was identified to be the "IS_SUCCESSFUL" column (represented as either 0 or 1)
- The "EIN" and "NAME" columns were droped s they did not offer any relevant data for our model. 
- The remaining columns became the features for the model.
- A density plot was created to determine a cutoff point to bin "rare" categorical variables together in a new column, Other. 
- Categorical variables were encoded using one-hot encoding
- The preprocessed data was split into features and target arrays and into training and testing datasets
- Standardized numerical variables using Scikit-Learn’s StandardScaler

### 2) Compiled, Trained, and Evaluated the Model

The number of neurons was determined by the length of the X_train_scaled variable which contains the number of features in the dataset. 
Two neurons were picked as they had the most accurate results when using the tensorflow playground. The number of neurons in subsequent attempts was altered using the standard rule of 2-3 times the number of features. 

Attempt 1

- 2 Hidden Layers
- 12 neurons (Layer1), 6 neurons(Layer2)
- Used Relu and Sigmoid Activations Functions since sigmoid is best for binary classifcation and relu for nonlinear relationships.
### Accuracy: 73.3%

Attempt #2

- 3 Hidden Layers
- 150 neurons (Layer1), 90 neurons(Layer2), 80 neurons(Layer3)
- Used Relu and Sigmoid Activations Functions 
- Removed "USE_CASE_Other","AFFILIATION_Other" columns, and "STATUS" as it consisted of mostly 1s (which mean the organization is currently active).
### Accuracy: 72.5%

Attempt #3

- 3 Hidden Layers
- 80 neurons(Layer1), 40 neurons(Layer2), 25 neurons (Layer3)
- Used Relu and Sigmoid Activations Functions 
- Went back to original dataset
##Accuracy: 72.4%


## Summary 

- The most optimal model achieved a 73% accuracy score. For improvement, more data is required to include features such as how long the organization has been in operation for.

