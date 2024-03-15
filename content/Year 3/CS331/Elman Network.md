> The **Elman network** is a type of [[Recurrent Neural Network]].

![[Screenshot 2024-03-14 at 14.34.12.png|200]]

We consider the feedback edge as being a self-loop.

## Example
Consider an Elman network with one internal node, which has a $\tanh$ activation function:

![[Screenshot 2024-03-14 at 14.38.58.png|200]]

We can then represent the output of the internal node as:
$$
a_t = W_i \cdot x_t + W_h \cdot a_{t-1}
$$
Any biases are added accordingly.