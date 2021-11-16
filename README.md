# Alphbet_Soup_Funding_Predictor

   Using TensorFlow I have designed a neural network, or deeplearning model, to create a binary classification model that can predict if an Alphabet Soup-funded organisation will be successful based on the features on the dataset given. 

## To prepare the data for analysis I took the following steps:
> * dropped the unnecessary columns of EIN and Name.
> * placed all of the outliers for the columns 'Application Type' and 'Classification' (I eventually did the same with 'Ask Amount' in an attempt to increase accuracy in the model.)
> * applied One-Hot encoding to the dataframe. 
> * split the data into feature and target arrays.
> * split the data into training and testing datasets. 
> * scaled it using StandardScaler.

> ![image](https://user-images.githubusercontent.com/83737584/141922308-c8432d4a-48f1-420b-aa67-79c6ac5c6553.png)

## Compile, Train, and Evaluate the Model
> After attempting to manually determine the model of best accuracy, I decided to determine the optimal function, number of hidden layers, epochs, and nuerons for the model I needed to create a method allowing KerasTuner to test for all of these parameter and determine the model of best accuracy. Over 600 models were attempted to determine the best model and hyperparameter features.
> ![image](https://user-images.githubusercontent.com/83737584/141923041-9959c7d5-0e2e-46fa-a6e9-d4e70dc1cbe3.png)

> ![image](https://user-images.githubusercontent.com/83737584/141923280-bf658fc5-fe8e-4858-8555-b3cbc2a9dad8.png)




<hr>
Contact:

* https://www.linkedin.com/in/sharon-colson
* sharon.colson@gmail.com
