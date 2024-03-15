> RNNs are a type of [[Artificial Neural Network]]. They differ from [[Feedforward Neural Network|feedforward neural networks]] in the fact that the output of a given layer *can* affect earlier layers at a later time. That is, the flow of information is bi-directional.

RNNs are particularly useful for temporal data (as it utilises a form of internal memory). As such, the input order is important.

The internal memory is used to affect the result of the state at the next timestep.
Consider an RNN moving through time, with a single layer (with a linear activation function). We can see the result based on the memory cell for the inputs $\{1,2,3\}$:

![[Screenshot 2024-03-14 at 14.31.39.png|300]]

Two variations of a *simple* are:
- [[Elman Network]]
- [[Jordan Network]]

More complex examples are:
- [[Deep Recurrent Neural Network]]
- [[Bidirectional Recurrent Neural Network]]

Some RNNs solve the [[Activation function#Sigmoid|vanishing gradient]] problem:
- [[Long Short-Term Memory]]