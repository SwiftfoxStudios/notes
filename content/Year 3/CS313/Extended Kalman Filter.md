> Generally, a Taylor Approximation can be used to linearise a nonlinear function. This is utilised in the EKF as an extension to the [[Kalman Filter]].

*Prerequisite: [[Kalman Filter]]*

The EKF approach working is dependent upon two main factors:
- **The degree of uncertainty** - a wider variance in belief means nonlinearities cause a greater effect in predictions.
- **The degree of local nonlinearity** - a highly nonlinear function means local Taylor approximations become invalid.

We can create our transition model (accounting for both movement and control inputs) as a function:
$$
x_t = g(u_t,x_{t-1})
$$
We can also consider our observation model:
$$
z_t = h(x_t)
$$
We can linearise a nonlinear function by using a linear function that is tangent to the nonlinear function at the point of our state (mean, $x^+_t$).

We use the *[[Jacobian Matrix]]* of our transition and observation models in our calculations of our posteriori estimates. This is computationally expensive.