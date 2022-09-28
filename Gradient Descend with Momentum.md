# Gradient Descent with Momentum
<a href = "https://machinelearningmastery.com/gradient-descent-with-momentum-from-scratch/">Link</a>

Gradient Descent with Momentum is a process algorithm continually calculates and updates the downward direction of a multi dimensional space moves until it reaches the absolute minimum. 

- does this by starting the calculate the gradient (multi dimensional derivative) to know what direction is downward
- then calculates the steps size it will take to go the new location
- from the new location, the process repeats again and again until it reaches the minimum

## Gradient Descent
: optimization algorithm (first order algorithm)

- Gradient
: 1st order derivatives for a multi-variable objective function

<mark>what is an objective function?</mark>

- the purpose of Gradient Descent is to locate the minimum of the function
- refers to a minimization optimization algorithm that follows the negative slope of a multidimensional space down to the minimum point of the target function
- requires:
  - target function being optimized
  - derivative of the object function
  - starting point (x) - randomly selected

## Going Downwards
1. Derivative is calculated at the randomly selected (x) point to know the direction of the downwards movement
2. Then the distance to move in the in space is calculated by: 
$$ x = x - stepsize*f'(x) $$

- the steeper the objecttive function
  - larger the magnitude of the gradient at the point
  - the larger the step size will be
- step_size
: hyperparameter that controls how far to move in space
- learning rate
: gradient each iteration of the algorithm

## Momentum
- accelerate the optimization process
- decrease the number of function evaluation

**Why it is called Momentum?**

- based on physics analogy
- acceleration in a direction can be accumulated from past updates
- the negative gradient is a force moving a particle through parameter space
- change in parameters
$$ChangeX = stepsize*f'(x)$$