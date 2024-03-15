> A Bayes filter forms a discrete belief about an environment for [[state estimation]] using [[Bayes' Theorem]].

Notably, we have:
$$
\sum_x P(x) = 1
$$
When accounting for error or noise, we can represent a state as:
$$
P(\text{belief}|\text{truth})
$$
## Example
Given a set of observations, $z$, controls, $u$, true positions, $x$ and times $t$, we aim to find the likelihood of an event based on a belief and all previous measurements. 

Namely,
$$
\Huge P(x_t|z_{1:t},u_{1:t})
$$
We can use a recursive formulation of [[Bayes' Theorem]] to calculate this, **assuming all sensor measurements are independent**.

We have:
$$
\Huge\text{Belief}(x_t) = \eta P(z_t|x_t)P(x_t|z_{1:t},u_{1:t})
$$
N.B. $\eta$ is a normalisation constant.

Operating under the *Markovian assumption* that a state is solely dependent on the previous state, we can show:
$$
\Huge\text{Belief}(x_t) = \eta P(z_t|x_t)\int \biggl( P(x_t|u_t,x_{t-1})\cdot\text{Belief}(x_{t-1})\biggr)dx_{t-1}
$$
Namely, we have
- $P(z_t|x_t)$, our observation model
- $x_t|u_t,x_{t-1}$, the transition model
- $P(x_0)$, the prior

### Matrix Representation
We can use a matrix to represent this model:
$$
\Huge B(t)^T = \eta\cdot O_t\cdot T^T \cdot B(t-1)^T
$$
This is given an observation $O$ and state transition $T$.

We can see an example below, assuming two possible states L and R:
![[Screenshot 2024-01-30 at 16.56.59.png]]

Here, we have observed L.
Note that the $P(\text{observation}|\text{truth})$:
$$
P(L|L) = 0.9, P(L|R) = 0.2
$$
(these values are given)

Note our transition model, which states:
$$
P(L\to L) = 0.7, P(L \to R) = 0.3
$$
And the initial prior:
$$
P(L_{t=0}) = 0.5
$$
After the coefficient is determined, this results in a final state vector which shows the probability of being in L or R (*see rightmost vector*).