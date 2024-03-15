## Linear Regression
> Linear Regression generates a line of best fit in order to predict likely future values.

The hypothesis can be modelled as a line:
$$h_\theta(x)=\theta_0+\theta_1x$$
with the $\theta$ values representing the intercept and slope.
These can be optimised using *gradient descent*.
## Logistic Regression
> A logistic regression calculates the probability of a binary event, given historical data.

This is done by essentially fitting a dataset to a sigmoid curve. For example, when considering the *hours required on average to pass an exam*, below:
![[Screenshot 2023-11-20 at 15.09.25.png|300]]
This can be extended to multi-class classification, where the points should be fitted to a discrete number of values (classes). This is done using the **softmax** function.