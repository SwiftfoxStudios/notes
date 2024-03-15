> The UKF is a nonlinear state estimator which solves the issues of linear approximation in the [[Extended Kalman Filter]].

The UKF uses *sigma points* which follow the mean and covariance of the probability distribution. These points are transformed using the nonlinear function and an estimate of the Gaussian distribution of the state is made.

There is no need to compute *[[Jacobian Matrix|Jacobians]]*, making it simpler, more efficient **but** more computationally expensive.