> A loss (*or cost*) function is a function used to represent the difference (error) between a predicted outcome and an optimised target value, $L(\hat{y},y)$.

The value of the function follows the properties:
- Minimised when the error is small
- Increasing as the error increases
- Continuous and Differentiable
- Convex
## $L_1$ Loss (Absolute Error)
> The $L_1$ loss is the absolute value of the error. It is not differentiable at $L(\hat{y},y)=0$.

This is:
$$
L(\hat{y},y) = |\hat{y}-y|
$$
This is generally equivalent to the *Manhattan Distance* in all dimensions.
The average value of the absolute error over a dataset is the *Mean Absolute Error*.

## $L_2$ Loss (Squared Error)
> This is the square of the error. Namely:
$$
L(\hat{y},y) = (\hat{y}-y)^2
$$

As this uses the square, it is sensitive to outliers. This is generally equivalent to the *Euclidian Distance* in all dimensions.
The average of the squared error over a dataset is the [[Mean Squared Error]].

## Log Loss (Cross-Entropy)
This is a measure of the loss between possible states.
$$
L(\hat{y},y) =- y\log\hat y-(1-y)\log(1-\hat y)
$$
Note, the partial derivative of this can be derived, with the chain rule on $u=1-\hat{y}$ as:
$$  
\begin{align}  
\frac{\partial}{\partial\hat{y}}\Bigl( -y\log\hat{y} \Bigr) - \frac{\partial}{\partial\hat{y}}\Bigl( (1-y)\log(1-\hat{y}) \Bigr) \\
= -y\frac{1}{\hat{y}} - (1-y) \cdot -1\frac{1}{u}\\
= -\frac{y}{\hat{y}}+\frac{1-y}{1-\hat{y}}
\end{align}  
$$
