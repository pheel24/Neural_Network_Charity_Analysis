# Neural Network Charity Analysis

## Overview
  In this project, the goal was to optimize charitable investment for a ficticious company, AlphabetSoup. To accomplish this, a dataset containing information about over 30,000 charities was subjected to a deep learning binary classifier, to bifurcate the data into charaties worth investing in and those that are not (encoded as 1 and 0 respectively). Before training, the data was subjected to preprocessing in the form of noisy feature removal and scaling. Following compilation, training, and evaluation, the model was optimized with extra neurons, extra hidden layers, and alternative activation functions. 
  
## Results
### Preprocessing
* Target: the target variable was the 'Is_Successful' column
* Features: the included features for this model were: 
  APPLICATION_TYPE—Alphabet Soup application type,
  AFFILIATION—Affiliated sector of industry,
  CLASSIFICATION—Government organization classification,
  USE_CASE—Use case for funding,
  ORGANIZATION—Organization type,
  STATUS—Active status,
  INCOME_AMT—Income classification,
  SPECIAL_CONSIDERATIONS—Special consideration for application,
  ASK_AMT—Funding amount requested,
Many of these were later encoded into categorical variables, leading to a greater number of features utilized than shown above. 
* Two columns, 'EID', and 'NAME' were unhelpful for training/testing purposes, and were dropped out of the model. 

![Capture1](https://user-images.githubusercontent.com/95315957/171772679-499a48a7-f7cc-42ba-93a3-726486729c65.PNG)

### Compiling, Training, and Evaluation
* Intially, the model contained two hidden layers with 8 and 5 neurons respectively, utilizing the 'relu' activation function, with one output layer utilizing the 'sigmoid' activation function. 

![Capture2](https://user-images.githubusercontent.com/95315957/171773616-5233e542-12f2-49e1-a058-07765d52bcaa.PNG)

* Upon achieving a ~.70 accuracy score, the following methods were employed to optimize the classifier:
*   Alternative activation function: instead of 'relu' I tried the 'tanh' function
*   Extra neurons: I added even more neurons to the existing hidden layers, increasing from 8 and 5 to 150 and 100 respectively
*   Extra hidden layer: I added an additional hidden layer using 'tanh' consisting of 5 neurons

![Capture3](https://user-images.githubusercontent.com/95315957/171773650-6b139e4d-929b-4e29-a3a5-0b2f9063c788.PNG)

Even with these extra optimization efforts however, the model did not surpass the accuracy goal of 75%, peaking at 73.3%

![Capture4](https://user-images.githubusercontent.com/95315957/171773890-aad7734d-bd7d-432e-aca6-6095d3cf6b14.PNG)

## Summary
This model proved sufficent in its goal in my estimation. Using the model to buttress decisions about investment would certainly help improve the business model. While the accuracy is not high enough to simply trust the model in all cases, it could serve as a useful supplementary resource to investment decisions. 
A gradient boosted model could do a better job of classifying this data, as it would add more forests and layers without simply adding more neurons as I did. This does come with the risk of overfitting however, which could be partially accounted for by moving the data to a database which could pipe new entries into the model in real time. 
