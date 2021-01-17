# Neural Network CharityAnalysis
## Purpose
Analyze Alphabet Soup’s business data containing more than 34,000 organizations that have received funding to create a binary classifier that is capable of predicting whether future applicants will be successful if funded.
## Results
### Data Preprocessing
- What variable(s) are considered the target(s) for your model?

Since our main goal is to predict if future applicants will use the funding effectively the target for the model was selected to be "IS_SUCCESSFUL"
- What variable(s) are considered to be the features for your model?

APPLICATION_TYPE, AFFILIATION,CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT are considered for the model.
- What variable(s) are neither targets nor features, and should be removed from the input data?

At a first glance "EIN" and "NAME" were not consider given that they are identifiers and they don't contribute to the model. After encoding the data it was realized that "SPECIAL CONSIDERATION" is dichotomous; hence "SPECIAL_CONSIDERATIONS_Y" was not longer considered an input.
### Compiling, Training, and Evaluating the Model
- How many neurons, layers, and activation functions did you select for your neural network model, and why?

The model had e layer; the first one with 80 neurons doubling the number of inputs, the second layer had 30 neuron. Activation function used was relu and later chandged to sigmoid.
- Were you able to achieve the target model performance?

Unfortunately, it was not possible to increase the accuracy over 75%
- What steps did you take to try and increase model performance?
The steps taken to improve accuracy were to analyze the data and remove inputs that won't contribute to the model, change the activation function,  increase the number of layers and neurons, and try to eliminate outliers. 
## Summary
### 1st optimization
"SPECIAL_CONSIDERATIONS_Y" was not longer considered and activation functions all were set up to sigmoid since data was scaled and the model ahould be binary classification. Testing accuracy remained at 72%. 
### 2nd optimization
A third hidden layer was added to the model, this layer included 10 neurons. Number of epoch was reduced to 60 due to computational power. At risk of overfitting it was decided to add the 3rd layer to try to discover potential relationships and increase the model accuracy; with test accuracy remiaing at 72% it is concluded that there is no need for the added layer.
### 3rd optimization
After analyzing the data it was discovered that "Asked Amount" varies significantly from $5k up to $8B. Considering neural networks are sensitive to such variations it was decided to filter the data keeping all information below $110000. The first model was trained with the new subset of the data. Model accuracy increased to 73%, it doesn't justify not using 15% of the data set.

Using random forest the same level of accuracy can be achieved. Less coding is needed and the ability to interpret what is happening is higher than in ANN. 
