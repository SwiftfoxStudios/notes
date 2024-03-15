> FNNs are one of two broad categories of [[Artificial Neural Network]]. It is characterised by a unidirectional flow of information through the network. This contrasts with [[Recurrent Neural Network|recurrent neural networks]], which are bidirectional.

Typically, in FNNs, *forward propagation* occurs. This means the output for a layer is solely dependent on its inputs from a previous layer. We can use this to predict the outcome of a network based on a set of inputs, [[activation function]]s and weights.

Specifically, we note that for a vector of inputs, $x$, matrix of weights, $W$ and vector of node biases, $b$, we find:
$$
z = W \cdot x + b
$$
After applying the [[activation function]] to $z$, we have:
$$
a = \text{activation}(z)
$$
This output value for a layer can be used as inputs to consequent layers.

Also, [[Backpropagation]] occurs, which acts as the trainer for the neural network.


