
# Hyperparameter
<a href = "https://towardsdatascience.com/what-are-hyperparameters-and-how-to-tune-the-hyperparameters-in-a-deep-neural-network-d0604917584a#:~:text=Deep%20Neural%20Network%3F-,What%20are%20hyperparameters%3F,optimizing%20the%20weights%20and%20bias).">Link</a>


hyperpararmeters
: variable which determines the network structure and how the network is trained

- set before training happens

1. Number of Hidden Layers and Units
2. Underfitting and Overfitting
3. Dropout 
4. Learning Rates
5. Momentum

## Number of Hidden Layers and Units

<img src = "https://images.deepai.org/glossary-terms/4c9d8f89916848b4803df475ef6892be/hiddenlayer.png">

- Layers are different processing stages or qualification that a Network Structure contains
- Hidden Layers 
: the layers between the input layer and the output layer
- Hidden units
: have regularization techniques to increase accuracy
  - hidden units are within hidden layers
  - less number of units may cause underfitting

## Underfitting and Overfitting
<a href = "https://www.geeksforgeeks.org/underfitting-and-overfitting-in-machine-learning/">Link for Notes</a>
<br>
<img src = "https://www.dropbox.com/s/nlmx0o7mdjraca2/Screenshot%20from%202022-07-28%2018-15-19.png?raw=1" width = 375px>
<img src = "https://www.dropbox.com/s/q6n6ezzbagakv20/Screenshot%20from%202022-07-28%2018-15-07.png?raw=1" width = 375px>

overfitting
: when the Machine Learning Algorithm get overtrained or "overspecialized" that it cannot make accurate predictions on testing data

- similar to how a organic chemistry scientist cannot do chemistry if a molecule does not have carbon in it 
- happens when the model is overtrained with so much data, it start learning from the irrevalent part (noise) of the Dataset
- Result in the Data not be able to categorize the data

underfitting
: the Machine learning algorithm cannot capture the underlying trend of the data

- the AI Model perform well on the training models but cannot with test models
  - similar to how a student performs well on homework assignments but doesn't on exams
- destroys the accuracy of our machine learning model 


Bias
: assumption made by a model to make a function easier to learn. It is the error rate of the training model
- high error rate, high bias
- low error rate, low bias

Variance
: error rate of the testing data
- high error rate, high variance
- low error rate, low variance

<div>

## Dropouts 
Dropout
: regularization technique to avoid overfitting

- Dropouts is implemented per- layer in Neural Network
-  by randomly dropping out nodes during training prevents the Model from overfitting
- the Default interpretation of the dropout hyperparameter is the probability of training a given node in a layer
- good dropout value is between 0.5 to 0.8

## Learning Rate
<img src = "https://www.dropbox.com/s/nm5hl0b8dadeqgs/Learning%20Rates.png?raw=1" width = 450px>

Learning rate
: tells how quickly a network updates its parameters

- a low learning rate - slows down the learning process of the network but converges smoothly
- large learning rate - speeds up the learning but nay not converges as smoothly
- Decay Learning Rate
: learning starts off learning fast and then slows down after each epochs
  - a preferred technique for training modern neural networks

## The Momentum of Neural Networks
Momentum
: helps the direction of the next step with the knowledge of previous steps

- "speeds up" the Gradient Descent toward the minimum of the target function

- prevents oscillation (noise of a dataset)
- typical range of Momentum is between 0.5 and 0.9

## Batch Size
- Mini batch size is the number of sub samples given to the network after which parameters update happens
- good default size : 32, 64, 128, 256

