> This is a linear [[Gaussian Filter]].

We make some assumptions when using the Kalman Filter. Namely:
- The initial state is normally distributed.
- The system is linear.
- The noise is normally distributed.
- The transitions between states are Markovian.

## Priori (Predict)
### State Estimator
Consider a robot which has a position and velocity. We assume constant acceleration for simplicity, but in reality, this increases the dimension of our calculations by 1.

Hence, we have, at timestep $k$:
$$
x_k = \begin{bmatrix} x \\ \dot{x} \end{bmatrix}
$$
We can then propagate an estimate for the position and velocity after a given change in time, $\Delta t$, using the transition matrix $F$, such that:
$$
Fx_{k} = \begin{bmatrix} 1 & \Delta t \\ 0 & 1 \end{bmatrix}
\begin{bmatrix} x \\ \dot{x} \end{bmatrix}
$$
If we have a *control input*, $B$, this would also affect this measurement, namely $Bu_k$. Assuming this isn't the case, we have an estimate:
$$
x_{k}^- = Fx_{k-1} + w_{k}
$$
where $w$ is zero-mean Gaussian noise.

We then have a priori estimation of the state. The superscript minus ($x^-$) means the estimate is a prior prediction (before the update step).

### Covariance Estimator
We also require knowledge of the spread of our prediction - this is dependent on the process noise and the covariance at the previous timestep. We have:

$$
P^-_k = FP_{k-1}F^T + Q
$$
given our transition matrix, $F$, from before, and the variance of the process noise, also from before ($w_k \sim \mathcal{N}(0,Q)$).

## Kalman Gain
We should consider what weighting an observation (measurement) has, compared to a prediction, based on their respective variances. A smaller variance means a larger contribution to the state estimate.

Given a measurement model $C$, we can form the Kalman gain, based upon the [[#Covariance Estimator]] and the measurement noise, $v_k \sim \mathcal{N}(0,R)$:

We have:
$$
K_k = \frac{P^-_kC^T}{CP^-_kC^T+R}
$$

## Posteriori (Update)
We can then form a posterior prediction (output) from our determined priori and Kalman gain. This is the **update** step.

### State Estimator
We use the priori and the Kalman gain to determine the state. We have $z_k$ here, which is the observation at time $k$:
$$
x^+_k = x^-_k + K_k(z_k - C_k \cdot x^-_k)
$$

### Covariance Estimator
We can then form an estimate of the covariance at time $k$. This is:

$$
P_k^+ = (I - K_kC_k)P^-_k
$$

Where $I$ is the identity matrix.

We can then return $x^+_k,P^+_k$.
