> The **Jordan network** is a type of [[Recurrent Neural Network]].

![[Screenshot 2024-03-14 at 14.35.10.png|200]]

The feedback edge returns from the output node to the internal node.

## Example
Consider an Jordan network with one internal node, which has a $\tanh$ activation function:

![[Screenshot 2024-03-14 at 14.40.15.png|200]]

We can then represent the output of the internal node as:
$$
a_t = W_i \cdot x_t + W_h \cdot y_{t-1}
$$
Any biases are added accordingly.