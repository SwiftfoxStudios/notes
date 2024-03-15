> This is a process in [[Machine Learning]] where we aim to find a local minimum.

We can define the gradient as the derivative of a [[Loss Function]].

Hence, the next 'step' when performing gradient descent can be calculated by:
$$
x_{t+1}=x_t-\alpha \frac{df}{dt}
$$
Where $\alpha \in (0,1)$ is given as the learning rate. Specifically, it controls the speed at which a move is made (an increase in $\alpha$ means larger jumps, which could overshoot a local minimum).


