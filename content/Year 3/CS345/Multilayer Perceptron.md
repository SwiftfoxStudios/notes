> This is a simple deep learning method. Unlike [[Regression|regression]], it is a nonlinear classifier - that is - it can classify data that is linearly inseparable.

## Activation Function
This is a function that maps weighted inputs into the outputs of each [[Neuron|neuron]], in effect, *squishing* the real number line. Commonly, a [[Regression#Logistic Regression|logistic function]] is used. Other scaling functions, such as the hyperbolic tangent function, can be used.

## Training
The [[Artificial Neural Network|neural network]] uses backpropagation to train the model. Gradient descent is typically used to minimise the cost function at a given layer, calculated as the deviance in the accuracy of the current value of each neuron. The *least squares* method is commonly used here, such that:
$$\sum (n_{current} - n_{new})^2$$ In practice, this is often power inefficient, so an alternative - *stochastic gradient descent* - where a random sample is used to calculate the 'next move', is often used.