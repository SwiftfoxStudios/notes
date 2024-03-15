> The McColluch-Pitts Neuron was the first computational model of the [[Neuron|biological neuron]]. It utilises binary inputs of equal weights; a limitation addressed by the development of the [[perceptron]].

As seen in the table below, the model consisted of inputs (dendrites) and an output (axon), with internal processing (soma) and weights between neurons.

![[Screenshot 2024-01-27 at 18.10.42.png]]

## Operation
Inputs are binary and can be one of two kinds:
- **Excitatory** inputs count towards excitation.
- **Inhibitory** inputs prevent excitation. If any are 1, excitation fails to occur.

Each neuron has a threshold value, $\theta$, at which the neuron is excited. 

![[Screenshot 2024-01-27 at 18.24.13.png|400]]

This can be represented in a Rojas Diagram (*see above*).
We can represent the [[Activation function|function]], **given no inhibitory inputs are 1**, as such:
$$
\begin{equation}
  H_\theta(x)=\begin{cases}
    1, & \text{if $x\ge\theta$}.\\
    0, & \text{if $x<\theta$}.
  \end{cases}
\end{equation}
$$
This could be generalised to a vector of inputs.
Naturally, the sum of all values in a vector is equal to the dot product of the vector and the 1-vector:
$$\sum_{i=0}^\text{length($v$)}(v_i) = 1 \cdot v $$

## Forming Logic Gates
> We can form logic gates with these neurons.

Two simple examples:
- A NOT gate is simply a neuron with $\theta = 0$ and a single inhibitory input.
- An N-INPUT AND gate is a neuron with $\theta = N$ and $N$ excitatory inputs.
