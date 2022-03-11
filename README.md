# Neural Network Charity Analysis

## Overview
Supporting organizations by funding them entails risks, as some organizations might not succeed in the goals they sent up for themselves. The objective of the present work was to create a binary classifier that is capable of predicting whether applicants will be successful if funded. The data used here includes information on more than 34,000 organizations that have received funding from the charity Alphabet Soup.

## Results
### Data Preprocessing
The raw dataset including 34,299 rows and 12 columns was first preprocessed to prepare it for the Neural Network Analysis. Steps in data preprocessing included:

- Dropping two identification columns, "EIN" and "NAME".
- Identifying categorical variables with more than 10 unique values. Two columns were identified: "APPLICATION_TYPE" with 17 and "CLASSIFICATION" with 71 unique values.
- Binning "APPLICATION_TYPE" and "CLASSIFICATION" unique values based on the density plots of the value counts. See plots below. The "APPLICATION_TYPE" values with count less than 500 were binned together decreasing the number of unique values to 9. The "CLASSIFICATION" values with count less than 1500 were binned together decreasing the number of unique values to 6.

![alt text](https://github.com/floramatos/Neural_Network_Charity_Analysis/blob/main/Images/application_plot.png?raw=true)
![alt text](https://github.com/floramatos/Neural_Network_Charity_Analysis/blob/main/Images/classification_plot.png?raw=true)

- Transforming the categorial variables into dummy variables using one-hot encoding.
- Splitting the data into features, X = 43 independent variables, and target, y = 1 dichotomic dependent variable ("IS_SUCCESSFUL": measured whether the money was used effectively), arrays.
- Splitting the dataset into training and testing datsets.
- Standardizing the distribution of the numeric independent variables (Mean = 0, SD = 1).


### The Neural Network Model
The next step was to design a neural network model to create a binary classification model that can predict if a funded organization will be successful based on the features in the dataset.

Neural Network model characteristics:
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

After running through 100 epochs, the model loss was still high at 4.48 and its accuracy was lower than ideal, explaining only 61% of the outcomes. Further steps are needed to improve the neural network model.

*** Add model summary, loss and accuracy values

### Model Optimization
The final step in the analysis consisted to model optimization. As the initial neural network model only achieved 61% accuracy, two attemps were made to improve the model with a target predictive accuracy higher than 75%.

Method 1 - Changing data preprocessing
Given that two columns containing identification were dropped in the data preprocessing stage, it was tested whether keeping the "NAME" column, containing funded organizations names, would improve the model. The new model with 48 input variables, although showing an improved loss of 1.01, explained only 53% of outcomes.

*** Add model summary, loss and accuracy values

Method 2 - Evaluate different hyperparameters
A function letting kerastuner identify the best activation function and number of neurons for each layer was created to evaluate different hyperparameter options.

Optimized Neural Network model characteristics:
	- Input:
		- 43 features
	- First hidden layer: 
		- 80 neurons
		- Tahn activation function
	- Second hidden layer: 
		- 30 neurons
		- Relu activation function
	- Output:
		- 1 target
		- Sigmoid activation function

*** Add model summary, loss and accuracy values

## Summary
In sum, the present project aimed at building a neural network prediction model to determine whether applicants to a fund wwould be successful if funded. The first Neural Network model created with two hidden layers using Relu as activation function achieved 61% of accuracy. A second optimized model consisting of ... hidden layers with Tahn as activation function achieved ... of accuracy. The goal of achieving a target predictive accuracy higher than 75% was ... schieved.