> **Backpropagation** is the main method of [[Neural Network Training|training]] a [[Feedforward Neural Network]] through [[gradient descent]].

## Motivation: Chain Rule
The motivation behind backpropagation is a dependency network for calculating complex multivariate chain rule derivatives.

For example:
$$
z=\sin(2x+y)
$$
We can then represent the partial derivatives of one of the functions as:
$$
a = 2x+y \implies a_x = 2, a_y = 1
$$
Hence:
$$
z = sin(a) \implies z_a = cos(a)
$$
So we can then have the edges:
$$
z_a \to a_x \text{ and } z_a \to a_y
$$
Showing the multivariate dependencies.

## Example
> Note - to save computation, we can *cache* backpropagated paths.

Considering a neural network, we can calculate the backpropagated loss values for a given node by summing the products of the partial derivatives of the paths to that node from the output.

Hence, consider the following network with inputs $(0,1,0)$, target $y=1$ and [[loss function]] $L(y,\hat{y}) = \frac{1}{2}(y-\hat{y})^2$:

![[Screenshot 2024-03-13 at 18.25.48.png|200]]
Suppose we wish to calculate the error derivative $\frac{\partial L}{\partial w_5}$.
Assume forward propagation has occurred, hence:
$$
\begin{align}
z_1 = -2&, a_1 = -0.964 \\
z_2 = 4&, a_2 = 0.9993 \\
z_3 =0.1073&, \hat{y} = 0.5268 \\ 
\end{align}
$$
We then find the paths leading $L \to w_5$, of which there is only one.
We then note the functions that lie on this path:
$$
\begin{align}
L(y,\hat{y}) &= \frac{1}{2}(y-\hat{y})^2 \\
\hat{y} &= \sigma(z_3) \\
z_3 &= a_1w_7 + a_2w_8 + b_3 \\
a_1 &= \tanh(z_1) \\
z_1 &=w_5x_3 + w_3x_2 + w_1x_1 + b_1
\end{align}
$$
We then determine their *local* partial derivatives:
$$
\begin{align}
\partial L_\hat{y} &= \hat{y}-y \\
\partial \hat{y}_{z_3} &= \hat{y}(1-\hat{y}) \\
\partial z_{3}{a_1} &= w_7 \\
\partial a_1z_1 &= 1-a_1^2 \\
\partial z_1w_5 &= x_3
\end{align}
$$
We can then simply take the product of the partial derivatives (and input the cached values):
$$
\partial L_{w_5} = (0.5268 -1)\cdot 0.5268(1- 0.5268) \cdot 3 \cdot (1-(-0.964)^2) \cdot 1 = -0.025
$$
