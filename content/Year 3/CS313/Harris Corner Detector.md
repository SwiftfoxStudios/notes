> This is a type of [[Feature (& Corner) Detection|corner detector]] used in [[Vision|computer vision]].

The HCD is invariant to rotations and are partially invariant to changes in intensity. For a corner detector that is invariant to scaling, the [[Scale Invariant Feature Transform]] is used.

The intuition behind the HCD is that an imaginary *shifting window* moved in either the $x$ or $y$ direction at a corner will result in a large variance in intensity values.

Consider a sample of size $(u,v)$ and a sliding window $W$ that shifts by $(x,y)$

We can form a structure tensor which characterises the distribution of the gradient of pixel intensities within a neighbourhood. Namely, it is essentially a non-normalised covariance matrix.

This is:
$$
M = \sum_{\{x,y\} \in W} \begin{bmatrix} I^2_x & I_xI_y \\ I_xI_y & I^2_y \end{bmatrix}
$$
With eigenvalues $\lambda_1,\lambda_2 = I_x,I_y$, we can show that:

![[Screenshot 2024-01-30 at 17.19.40.png]]

The intuition behind this is that the variance in intensity is large in both directions when a corner is present.