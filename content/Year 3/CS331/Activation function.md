> An activation function in an [[Artificial Neural Network]] is a function that characterises whether a neuron fires or not.

## Step Function
In [[MP Neuron|MP neurons]] and [[perceptron|perceptrons]], the step function is a simple instance of an activation function, characterised by the generated outputs:
$$
\begin{equation}
  H_\theta(x)=\begin{cases}
    1, & \text{if $x\ge\theta$}.\\
    0, & \text{if $x<\theta$}.
  \end{cases}
\end{equation}
$$

## Linear
A linear activation function can generate a real number of outputs, based on any input. It, however, has a constant derivative and in multi-layer networks, will not actually add functional layers, as a linear combination of linear functions is itself linear.

## Sigmoid
The sigmoid ($\sigma$) function returns a normalised output based on any input and has a smooth gradient.
$$
\sigma(x)=\frac{1}{1+e^{-x}}
$$
However, the sigmoid suffers from the *vanishing gradient* problem - at extrema, large changes in $x$ result in little change to the prediction; this can cause the model to be slow to learn. It is also computationally expensive.

## Hyperbolic Tangent
The $\tanh$ function is similar to the [[#Sigmoid]], but is *zero-centred*.
It is characterised by the equation:
$$
\tanh(x) = \frac{e^x-e^{-x}}{e^x+e^{-x}}
$$

## ReLU
The **Rectified Linear Unit** function is a variation of the [[#linear]] activation function that is flat for negative inputs. This is characterised by the function:
$$
\text{ReLU}(x) = \max(0,x)
$$
This does not have the *vanishing gradient* problem and also has a non-constant derivative, but suffers from the problem of *dying ReLU*, where neurons continually fail to activate, continually outputting 0 for negative inputs.

### Leaky ReLU
The *dying ReLU* problem can be solved by ensuring the negative side of the function also has a non-zero gradient. 
$$
\begin{equation}
  \text{Leaky ReLU}(x)=\begin{cases}
    x, & \text{if $x\ge0$}.\\
    \alpha x, & \text{if $x<0$}.
  \end{cases}
\end{equation}
$$Typically, $\alpha = 0.01$.

### Parametric ReLU
This is a variation of [[#leaky ReLU]] where $\alpha$ is a learnable parameter.

## ELU
The **Exponential Linear Unit** is linear for $x \ge 0$ and nonlinear when negative. It is characterised by the equation:
$$
\begin{equation}
  \text{ELU}(x)=\begin{cases}
    x, & \text{if $x\ge0$}.\\
    \alpha (e^x-1), & \text{if $x<0$}.
  \end{cases}
\end{equation}
$$
This is smoother at $x=0$ than [[#ReLU]] but is more computationally expensive and still has the vanishing gradient problem when negative.

## Softmax
> Softmax is a function that returns a vector of a probability distribution based on a given input vector.

## Maxout