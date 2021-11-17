# Alphabet_Soup_Funding_Predictor

**OVERVIEW:** Using TensorFlow I have designed a neural network, or deeplearning model, to create a binary classification model that can predict if an Alphabet Soup-funded organisation will be successful based on the features on the dataset given. 


## To prepare the data for analysis I took the following steps:
> * dropped the unnecessary columns of EIN and Name.
> * placed all of the outliers for the columns 'Application Type' and 'Classification' (I eventually did the same with 'Ask Amount' in an attempt to increase accuracy in the model.)
> * applied One-Hot encoding to the dataframe. 
> * split the data into feature and target arrays.
> * split the data into training and testing datasets. 
> * scaled it using StandardScaler.

> ![image](https://user-images.githubusercontent.com/83737584/141922308-c8432d4a-48f1-420b-aa67-79c6ac5c6553.png)

## About the Variables:
> * Target: IS_SUCCESSFUL
> * Unnecessary: EID and NAME
> * Featues: APPLICATION TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT

## Compile, Train, and Evaluate the Model
> After attempting to manually determine the model of best accuracy, I decided to determine the optimal function, number of hidden layers, epochs, and nuerons for the model I needed to create a method allowing KerasTuner to test for all of these parameter and determine the model of best accuracy. Over 600 models were attempted to determine the best model and hyperparameter features.

> ![image](https://user-images.githubusercontent.com/83737584/141923041-9959c7d5-0e2e-46fa-a6e9-d4e70dc1cbe3.png)

> ![image](https://user-images.githubusercontent.com/83737584/141923280-bf658fc5-fe8e-4858-8555-b3cbc2a9dad8.png)

## Efforts to achieve target model performance:
> * Allowed Kerastuner to cycle the data through over 600 models to try and locate the maximum accuracy.
> * Refiltered the ASK_AMT column to reduce outliers.
> * Manually attempted to increase accuracy by adding hidden layers, increasing epochs, increasing nuerons.
> * Tried every optimization algorithm in the Tensorflow documentation. I eventually chose adagrad. 

My records for these are stored in AlphabetSoupCharity.h5.

<hr>

## Part 2: Revisiting the Model:

> * Finally, I decided to take another look at the data. I decided to keep the organization names after realizing that there were many organizations that had applied for funding more than once. If that is the case, if an organization has applied for funding and their endeaver has been successful all five times my thought is that if it applies a sixth time it is more likely to receive funding. I chose to drop the Application Types and Classifications under the theory that these would bear little weight. I also dropped status as there were two status variables (active and inactive) and only 5 points in the dataset were classified as inactive. I binned the Names column with all organizations applying for funding less than 50 times being placed in the Other status; and I binned the Ask Amount column as I had previously. 

> ![image](https://user-images.githubusercontent.com/83737584/142071349-a0bb4169-52c3-49a1-9473-4e8629abbc10.png)

> * Once this was completed and the data had been split into train and test sets and scaled, I proceeded once again with Kerastuner which suggested I started with the following model.

> ![image](https://user-images.githubusercontent.com/83737584/142071570-b54112dd-918b-43b3-8609-01f3be2df2f1.png)


> * In the end, after slowly adding neurons and hidden layers and setting the random state to 2, I was able to get the testing set to produce an accuracy of above 75% with a loss of 0.4908. Additionally, the stratify paramet was turned "off" in the train/test split which did appear to add a slight change in accuracy and loss in the model. 

> ![image](https://user-images.githubusercontent.com/83737584/142137146-a10e400a-acd8-4feb-a9e6-9dc1a4ef7f3d.png)

> ![image](https://user-images.githubusercontent.com/83737584/142083467-d53cbe62-4dc8-4a8f-9b8b-bb01ef13b026.png)

My records for this model are stored in AlphabetSoupCharity_Optimization.h5.

## Summary:
> * The best accuracy that can be achieved at this time is 75.03%.  After giving this some though I might would try a different learning model such as Random Forest Classifier. Additionally, running the final model once more but leaving the Classification column might be my next step in this journey. 


<hr>
Contact:

* https://www.linkedin.com/in/sharon-colson
* sharon.colson@gmail.com
