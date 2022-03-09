# Neural Network Charity Analysis

## Overview
Betting on organizations by funding them entails risks, as some organizations might not succeed in the goals they sent up for themselves. The objective of the present work was to create a binary classifier that is capable of predicting whether applicants to a specific fund will be successful if funded. The data used here includes information on more than 34,000 organizations that have received funding from the charity Alphabet Soup.

## Results
### Data Preprocessing
The raw dataset including 34,299 rows and 12 columns was first preprocessed to prepare it for the Neural Network Analysis. Steps in data preprocessing included:
	- Dropping two identification columns, EIN and NAME.
	- Identifying categorical variables with more than 10 unique values. Two columns were identified: APPLICATION_TYPE with 17 and CLASSIFICATION with 71 unique values.
	- Binning APPLICATION_TYPE's and CLASSIFICATION's unique values based on the density plots of the value counts. The APPLICATION_TYPE values with count less than 500 were binned together decreasing the number of unique values to 9. The CLASSIFICATION values with count less than 1500 were binned together decreasing the number of unique values to 6.
	**** Include density plots???? Or bins?????
	- Transforming the categorial variables into dummy variables using one-hot encoding.
	- Splitting the data into features, X = 43 independent variables, and target, y = 1 dichotomic dependent variable (IS_SUCCESSFUL - was the money used effectively), arrays.
	- Splitting the dataset into training and testing datsets.
	- Standardizing the distribution of the numeric independent variables (Mean = 0, SD = 1).


### The Neural Network Model
The next step was to design a neural network model to create a binary classification model that can predict if a funded organization will be successful based on the features in the dataset.

Initial model characteristics:
	- Input:
		- 43 features
	- First hidden layer: 
		- 80 neurons
		- Relu activation function
	- Second hidden layer: 
		- 30 neurons
		- Relu activation function
	- Output:
		- 1 target
		- Sigmoid activation function

After running through 100 epochs, the model loss was still high at 4.482 and its accuracy was lower than ideal, explaining only 61% of the outcomes. Further steps are needed to improve the neural network model.

### Model Optimization
optimize your model in order to achieve a target predictive accuracy higher than 75%

Method 1 - Changing data preprocessing
keeping the "NAME" column, binning it and adding to the input variables (X = 48)

Method 2 - 

Data --- CSV containing  over the years. Columns that capture metadata about each organization:
	EIN and NAME—Identification columns
	APPLICATION_TYPE—Alphabet Soup application type
	AFFILIATION—Affiliated sector of industry
	CLASSIFICATION—Government organization classification
	USE_CASE—Use case for funding
	ORGANIZATION—Organization type
	STATUS—Active status
	INCOME_AMT—Income classification
	SPECIAL_CONSIDERATIONS—Special consideration for application
	ASK_AMT—Funding amount requested
	IS_SUCCESSFUL—Was the money used effectively

## Summary
