# Neural Network Charity Analysis


# Overview of the analysis: Explain the purpose of this analysis.

The purpose of this analysis was to create a neural network machine learning model using the dataset provided by Beks. We will creating a binary classifier model capable of predicting whether applicants will be successful if funded by Alphabet Soup.

# Data Preprocessing

We started our model creation process by processing the dataset and identifying our target and features for our model. Our target was the column titled "IS_SUCCESSFUL". This is the column which contains the values indicating whether or not the charity was successful in the past. Using this knowledge, we match up our target against our set of features. Which is provided by the other columns in the dataset containing more information in regards to the application type, affiliation, classification, use case, organization, income amount and special considerations. 

We did suspect we might not require all these features that we initially started testing with and during the optimization phase we did remove a combination of application types, classifications, and the special consideration features from our feature set. In our final attempt allowed, we optimized the model removing special considerations a specific application type and a specific classification type.

# Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

Initially the model was ran with a standard number of nodes which was three times the number of input features for the first hidden layer. This would be 132 neurons and for our second neuron, we went with 65, approximately half the number of neurons in the first layer.

The activation layer of choice at the time was linear for the first two hidden layers and sigmoid for the output layer since we are looking at a classification model. 

Unfortunately, the target model performance was not reached with these initial settings and we attempted to optimize the model further.

![first_attempt](https://github.com/rainmannyc/Neural_Network_Charity_Analysis/blob/34ecf699e381eecfa3c2b2c8602d1ecf89c7c2f2/Resources/charity_original_attempt.png)

In our first optimization attempt, we keep the activation functions the same, however we added an additional hidden layer also with a linear activation. We increased our neuron count for our first layer to 232 neurons with 116 for the second and 60 for our third hidden layer. Unfortunately, this resulted in our results getting a lower accuracy score of 0.719. 

We then tried optimizing our model by dropping the features we mentioned in the paragraph above (special considerations, a specific application type, a specific classification type) and adding 3 more layers and tons more neurons to the model. The first hidden layer started with 600 neurons, to 400, 300, 250, 100, and then 60 for our final hidden layer. The activations were all linear for the hidden layers. Again, this did not yield us better results than our initial model which was gave us an accuracy score of 0.7212.

On our third and final attempt, we kept the columns dropped, we kept the number of neurons and hidden layers, however we changed all activation to "relu" and our optimizer to "Adamax". On this try we were able to yield a higher score than the original score with a 0.7309, with the loss at approximately the same for all 3 attempts. However, this is still below the target we initially aimed for of 75%. 

![third_attempt](https://github.com/rainmannyc/Neural_Network_Charity_Analysis/blob/34ecf699e381eecfa3c2b2c8602d1ecf89c7c2f2/Resources/charity_third_attempt.png)

# Conclusion 

The model is performing at a decent accuracy, however we can certainly improve the model possibly with other classification models such as a random forest model or an Easy Ensemble AdaBooster model. If we used a random forest model, we may be able to interpret more significance in our features individually as opposed to the neural network model which can be a bit of a black box at times. We can then narrow down which features would be best to optimize our model without overfitting the model. 
