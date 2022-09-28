# MNIST Handwritten Digit Recognition in PyTorch

#### Table of Contents of Notes
1. Setting Up the Environment
2. Preparing the Dataset

#### Links
1. <a href = "https://nextjournal.com/gkoehler/pytorch-mnist">Link of the Notes</a>
2. <a href = "https://towardsdatascience.com/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way-3bd2b1164a53"> Convolution Neural Network</a>
4. Computational Graphs

 - builds a simple convolutional neural network
- Convolutional Neural Network
: a Deep learning algorithm which can take input image, assign importance (learnable, weights, and biases) to various aspects/ objects in the image and be able to differentiate one from the other
  - the Pre-Process required is much less as compared to classification algorithms

<center> ## Setting up the Environment
 </center>
- using Pytorch to recognize MNIST's handwriting digits in this article
- Pytorch
: very popular framework for deep learning
  - it has dynamic execution graphs, meaning the computation graphs is created on the fly
 - Computational Graphs
: graphs with equational data that are a form of directed graphs that represents a mathematical expression. 
  - Every node in the graph can contain either an operation, variable

#### Code:

		 import torch
		 import torchvision

<center> ## Preparing the Dataset 
</center>
- First, we have to define the hyperparameters

<mark>What are epochs in Neural Network?</mark>

- One Epoch
: when an Entire dataset is passed forward and backward through the neural Network ONCE
- the number of epochs defines how many times we'll loop over the complete training dataset

#### Code:
- setting hyperparametes

<mark> what is the log_interval?</mark>
<mark>What is the purpose for the random seed</mark>

<img src = "/home/mingye/Documents/Notes/Python/pics/Screenshot from 2022-09-01 10-37-22.png">

- `torch.manual_seed` - sets the seeds for generating random numbers. Generator object
- the purpose of the random seed, is for repeatable experiments and anything using random generation
- `cuDNN` use nondeterministic algorithms to disabled setting `torch.backends.cudnn.enabled - False`

<mark>what are nondeterministic algorithms? </mark>

- NonDeterministic Algorithm
: provide different outputs for the same inputs on different executions
  - Deterministic Algorithms
: can only produce a single output for a single input even on different runs

- TorchVision
: a library for Computer Vision that goes hand in hand in with Pytorch
  - is used to load the MNIST dataset
- Batch_size - 64 for training
- Size 1000 for testing on this dataset

**What is the different between training and testing? **
- Training is using the batches to train and teach the AI model
- Testing is actually using the AI model to predict handwritings

**What is activation function?**

**What is the difference between nonlinear and linear activation function?**

**What is  a tensor image?**

- Tensors are like buckets of numbers of a specific shape and a certain rank (dimensionalty)

- are used for Machine learning. Represents input data and output data
- the size of each dimension in a Tensor
- Ex: 3D Tensor image [width, height, color]

**what is normalizing?**

- `Normalize()` 
: (non-linear activation function) performs Lp normalization of a given tensor over a specified dimension
  
this normalize the tensor image with mean and standard deviation

MNIST dataset
: (Modified National Institute of Standards and Technology database) 
  - commonly used for training various image processing systems

#### Code:
- need DataLoaders for the Dataset
loading the MNIST dataset

- Global Mean: 0.1307
- Standard Deviation: 0.3081 (of the dataset)
- Using the Global Mean and Standard Deviation to Normalize 
- below are making two variables: 
1. train_loader (dataset used to train the AI model)
2. test_loader (dataset used to test the AI Model)

<img src = "/home/mingye/Documents/Notes/Python/pics/Screenshot from 2022-09-01 10-37-48.png">

<img src = "/home/mingye/Documents/Notes/Python/pics/Screenshot from 2022-09-01 10-37-22.png">

- PyTorch's DataLoader contains a few interesting option other than the dataset and batch size
- could use `num_workers>1` could be used to use subprocesses to asynchronously load data or pin_memory to speed up RAM to GPU transfers
- `pin_memory` to speed up RAM to GPU transfers

#### Code:

- Example of test_loader:

		examples = enumerate(test_loader)
		batch_idx, (example_data, example_targets) = next(examples)

		# printing Batch Size
		example_data.shape

- Result: one test data batch is a tensor of shape: [1000,1,28,28,28]. This means we have 1000 examples of 28 by 28 pixels in grayscale. It is also plottable on Matplotlib

		import matplotlib.pyplot as plt
		fig = plt.figure()
		for i in range(6):
			plt.subplot(2,3,i+1)
			plt.tight_layout()
			plt.imshow(example_data[i][0], cmap = 'gray', interplation = 'none')
			plt title("Cround Truth:{}".format(example_targets[i]))
		plt.xticks([])
		plt.yticks([])
		gig

## Building the Network
- using a 2 2D convolutional layers followed by two fully- connected layers.
- activation function
  - using rectified linear units (ReLUs)
  - use it as a means of regularization we'll use two dropout layers
-In PyTorch, a network can be created  by created a new class

- Import some Modules:

		import torch.nn as nn
		import torch.nn.functional as F
		import torch.optim as optim
- Creating the Network