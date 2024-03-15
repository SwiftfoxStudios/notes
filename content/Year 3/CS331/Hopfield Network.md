> A Hopfield network is a model to represent an [[artificial neural network]]. It is a type of [[Recurrent Neural Network]].

It relies on a given corrupted input, $x_0$, which is pulled towards an *attractor*, to the nearest stable, memorised fixed point, $x^*$ through time, similar to a potential field.

It does this through [[Associative Learning]].

## Example
We will consider a *discrete* Hopfield network over a pattern.
We define each element $x_i$ that characterises the state of a neuron $i$.
Therefore, $\forall i, x_i \in \{-1,1\}$ (for a Bipolar pattern)\*.

As the network is a type of [[Recurrent Neural Network]], it has feedback loops (but without self-loops), creating a complete graph. Hence, consider a Hopfield network with 4 neurons ($K_4$):

![[Screenshot 2024-03-14 at 13.09.32.png|200]]

\* We assume binary patterns are used throughout. *Binary patterns* use 0 instead of -1.
### Learning
> *See [[Hebbian Theory]] and [[Outer Product]]*

Hopfield networks learn through the [[Hebbian Theory|Hebbian learning rule]]. Given an edge connecting two nodes (neurons) $x_i,x_j$, we have $W_{i,j} = x_i \cdot x_j$.

Hence, we can form a weight matrix $W = x\otimes x^T - I$ for the example pattern vector $x$ with 4 neurons (4 cells):
![[Screenshot 2024-03-14 at 13.21.50.png|20]]
We can represent this with the vector $\begin{bmatrix}1 & -1 & -1 & 1\end{bmatrix}$, with $1$ corresponding to black cells and $-1$, white cells.

Hence, we find $W$ as:
$$
\begin{bmatrix}
1 \\ -1 \\ -1 \\ 1
\end{bmatrix}
\otimes
\begin{bmatrix}
1 & -1 & -1 & 1
\end{bmatrix}
-
I_4 =
 \begin{bmatrix}
0 & -1 & -1 & 1 \\
-1 & 0 & 1 & -1 \\
-1 & 1 & 0 & -1 \\
1 & -1 & -1 & 0
\end{bmatrix}
$$

#### Multiple Patterns
We may also define $W$ over multiple patterns. This is the average of the sum of their $W$ matrices. Namely,
$$
(\frac{1}{n}\sum^n_{i=1} W_i)-I
$$
### Training
The Hopfield network is trained by updating the states of each neuron at every time iteration, until a stable state is reached.

Namely, we can describe the state of the set of neurons at a given time $\vec{s}(t)$ as:
$$
\vec{s}(t+1) = F(W \cdot \vec{s}(t))
$$Given the activation function, $F$, for which we will use the $sgn$ function for bipolar patterns:
$$
\text{sgn}(x)=
\begin{cases}
1&, x \ge 0 \\
-1&, x < 0
\end{cases}
$$
A state is dependent on all other neurons, as the neurons are modelled as a complete graph.

// MISSING //

A stable state has been reached, as:
$$
\vec{x} = \text{sgn}(W \cdot \vec{x})
$$
