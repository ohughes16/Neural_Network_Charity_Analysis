# Neural Network Charity Analysis

## Overview of the analysis: Explain the purpose of this analysis.
The Alphabet Soup Charity was interested in developing a machine learning algorithm that used neural networks to determine the success of giving money to an organization based off of more than 34,000 previous recipients of funding from Alphabet Soup. The organization was interested in being able to identify if an applicant would effectively use the money that was given to them using this algorithm to optimize who they gave funding to.

## Results:

### Data Preprocessing

Variable considered the target for the model:

The target variable for the model is comes from the "IS_SUCCESSFUL" column as either a yes or a no (1 or 0). This is determined by whether or not the money given to the organization was used effectively.

Variable(s) that are considered to be the features for the model:
- Application Type
- Affiliation
- Classification
- Use Case
- Organization
- Income Amount
- Special Considerations
- Ask Amount

Variables that are neither targets nor features, and should be removed from the input data:
- EIN
- Name
- Status

### Compiling, Training, and Evaluating the Model

I first altered the number of features and model inputs for the dataset to see if I could pre-process the data differently to acheive higher model performance. I reduced the number of input features from 43 to 38 by removing the feature "Status" and  consolidating the number of options in the "CLASSIFICATION" feature and "APPLICATION TYPE" feature. 

I consolidated the classes in the 'APPLICATION TYPE' feature to group increase the size of the Other group by setting the count cutoff at 1000.  This reduced the number of Application Type features to T3, Other, T4, T6, T5, and T19. The data is predominately made up of T3 application types, so reducing these options I felt would help the model's performance. I also set the count cutoff for the 'Classificatin' feature at 1000 due to most of the datasets falling into the C1000 category. 

I tried many combinations of neurons, layers, and activation features to acheive the highest model performance as possible.  Initially, I attempted adding an additional hidden layer, coming in at 3 hidden layers.  The first layer had 20 neurons and 10 neurons in both the second and third layers. I also attempted altering the different activation functions from relu to tanh and received little impact on the accuracy of the model. 

To crosscheck the model, I attempted a random forest model to see what kind of accuracy I would get and that resulted in a lower accuracy score of 0.71.

I then looped through a list of different neuron values that incremented by 2 neurons and wrote the accuracy scores to a dictionary so I could identify what the highest accuracy score was with what number of neurons.  In doing this, I was able to acheive an accuracy score of 0.73.

## Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

Although the desired accuracy of 75% was not acheived with my model, I would say that the model's accuracy was close to solving this classification problem. I think that if there was more information on the significance of the model parameters and the number of features being evaluated could be brought down to a smaller number we would become closer to solving this classification problem. The Application type and Classification columns were skewed in the number of samples of certain features. If we narrowed down what we were most interested in this model classifying correctly, we could up the model's accuracy by eliminating a lot of model features. For example, if we were interested in focusing just on T3 application types, it would allow the model to focus on fewer features, potentially allowing for greater accuracy.
