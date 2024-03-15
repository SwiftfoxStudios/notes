> Specifically, the single layer perceptron, which is a binary (linear) classifier that has the ability to learn.

It can be seen as an extension to solve some of the issues with the [[MP Neuron]], which only allows for binary inputs, all with equal weight.

As

The perceptron uses a weighted sum of inputs to determine importance of input features. The inputs themselves are real numbers. The *threshold* can also be learnt automatically, rather than being manually set.

![[Screenshot 2024-02-02 at 13.21.12.png|400]]

## Bias
> There also exists a bias value, which acts as the y-intercept of the seperator splitting the plane into two sections. This means we have the classifier represented as $w\cdot x + b$ (*see below*)

In the example below, we have two inputs, $x_1,x_2$ with weights $w(x_1) = 3, w(x_2) = 1$ and bias $b=-3$.

![[Screenshot 2024-02-02 at 13.30.19.png|300]]

Consider the inputs $x_1 = 1, x_2 = 0$.
We then have:
$$
x_1w_1 + x_2w_2 + b = 1(3) + 0(1) -3=0
$$
We have $1 \ge 0$, so the neuron fires according to this specific [[Activation function]].

## Learning Rule
> The perception learns by adjusting weights and biases if a node is misclassified, essentially shifting the linear separator. It is affected by the *learning rate*, $\alpha$, which can adjust the speed at which the separator rotates.

### Detection of Misclassified Nodes
First, we use the angle between the vector describing a node's deviation from the separation line and the normal to the separation line (*which is also the weight, **w***), as seen below:

![[Screenshot 2024-02-06 at 09.58.27.png|300]]

We can say a positive misclassification has occurred when 1 is classified as a 0 (above, $angle(w,v)> 90$).
A negative misclassification occurs when the opposite is true ($angle(w,v)\le 90$)

### Update Plane
Whilst there exists a misclassified input, we can simply add the vector of the misclassified node (if positive, subtract if negative) to our vector of weights:
$$
w_{new} = w_{old} \pm v
$$
