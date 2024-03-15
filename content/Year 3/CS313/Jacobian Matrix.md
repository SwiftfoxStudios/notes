> The Jacobian Matrix of a multivariate function is the matrix which represents its first-order partial derivatives.

For the context of robotics, it can represent the linear approximations of a nonlinear function.

## Example
Consider a robot moving in a 2D environment with heading and position given by $(x, y, \theta)$ (the columns in the matrix below). We have, considering the control input (displacement) $\Delta_{x,y}$:
$$
x_t = x_{t-1} + \Delta_{x,y}\cos(\theta_t)+\sigma_{x,t}
$$
$$
y_t = y_{t-1} + \Delta_{x,y}\sin(\theta_t)+\sigma_{y,t}
$$
$$
\theta_t = \theta_{t-1} + \Delta\theta_t+\sigma_{\theta,t}
$$
We can then form a matrix based upon the partial derivatives as defined by the Jacobian:
$$
J(\mathbf{f}) = \begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n} \\
\end{bmatrix}
$$
Hence, for this specific case, we have:
$$
\begin{bmatrix}
\frac{\partial x_t}{\partial x} & \frac{\partial x_t}{\partial y} & \frac{\partial x_t}{\partial \theta} \\ 
\frac{\partial y_t}{\partial x} & \frac{\partial y_t}{\partial y} & \frac{\partial y_t}{\partial \theta} \\
\frac{\partial \theta_t}{\partial x} & \frac{\partial \theta_t}{\partial y} & \frac{\partial \theta_t}{\partial \theta}
\end{bmatrix}
$$
This evaluates to:
$$
\begin{bmatrix}
1 & 0 & -\Delta_{x,y}\sin(\theta_t) \\
0 & 1 & -\Delta_{x,y}\cos(\theta_t) \\
0 & 0 & 1
\end{bmatrix}
$$
This matrix now replaces our transition matrix in calculating the [[Kalman Filter]].