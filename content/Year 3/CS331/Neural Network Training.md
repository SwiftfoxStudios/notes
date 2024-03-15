> The process of training a neural network consists of several steps.

Namely:
1. Random initialisation of weights and biases ($w,b$) and a target $y$.
2. Perform [[Feedforward Neural Network|forward propagation]] to determine a predicted output $\hat{y}$.
3. Compute the result of the [[loss function]] on $y$ and $\hat{y}$.
4. Perform [[Backpropagation]] through [[gradient descent]].
5. Repeat this until the loss function is minimised.