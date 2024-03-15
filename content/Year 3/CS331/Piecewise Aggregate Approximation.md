> **PAA** is a method of [[Dimensionality Reduction Methods|dimensionality reduction]].

PAA splits the time series data into segments, identifying the mean of the segment and using that as the value for that time period:

## Example
Consider the time series data below, with intervals as shown:

![[Screenshot 2024-03-14 at 16.49.05.png|300]]

We find the mean of each segment as:
$$
\begin{align}
\text{mean}(x_1) &= 2.33 \\
\text{mean}(x_2) &= 8 \\
\text{mean}(x_3) &= 6.33 \\
\text{mean}(x_4) &= 4.33 \\

\end{align}
$$
A limitation of this is that we lose information about trends, as we are using a 0-order polynomial (constant approximation).

This can be mitigated by using [[Piecewise Linear Approximation]].

Another limitation is the need for a constant segment size. This is mitigated by [[Adaptive Piecewise Constant Approximation]].