# Elements of Neural Network Structure
<a href = "https://www.v7labs.com/blog/neural-networks-activation-functions">Notes Webpage</a>

<img src = "Pic/Neural Network Structure.png">

In the image above, you can see a neural network made of interconnected neurons. Each of them is characterized by its weight, bias, and activation function.

## Input Layer
- in this layer no computation is performed
- nodes here jsut pass on the information to the hidden layers
- Input layer just take in the raw dataframe

## Hidden Layer
- nodes of the layer is not exposed
- They provide abstraction to the neural network
- computation are performed
- all layers of the hidden layer uses the same activation function

## Output Layer
- final layer of the network that brings information together
- might use an activation function different from the hidden layer

## Feedforward vs. Backpropagation
- Feedforward Propagation - the flow of information occurs in the forward direction. The input is used to calculate some intermediate function in the hidden layer, which is then used to calculate an output. 

- aims to minimes the cost function by adjusting the network's weights and biases.

- cost function gradients determine the level of adjustment with respect to parameters like activation function, weights, bias

