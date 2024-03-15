> Particle Filters utilise samples (particles) to represent a probability density function of the prediction of a state at a given timestep. It uses this to generate a posterior estimate for **non-parametric models**.

We can represent the probability as either a *number of samples* or as a *weighted representation*.

## Sampling
> We generate the samples according to a proposal function. 

We can generate random points according to a distribution:

### Gaussian Sampling
We can generate random points in order to form a Gaussian:
$$
\frac{1}{2}\sum_{i=1}^{n}\text{rand}(-\sigma,\sigma)
$$
This generates $n$ normally distributed samples between $-\sigma,\sigma$.
### Rejection Sampling
Rejection Sampling consists of generating a set of random points along two axes, for example, $(x,y)$.

We can then 'reject' the points above the curve according to a chosen distribution. For example, for an exponential:

![[Screenshot 2024-03-08 at 13.53.38.png|400]]

### Importance Sampling
We can also use a proposal based on the importance of the value of a function at a given point. Namely, the weight of a particle is dependent on the difference between the importance and the 


## Algorithm
Then, we can form the particle filter algorithm, which loops between a prediction and correction step, for each timestep $t$, as:

1. Create a prediction set and a correction set.
2. Generate samples from the proposal distribution.
3. Generate weights based on a target distribution.
4. Draw $M$ weighted samples in order to resample at $t_{n+1}$.

### Within Localisation
> Specifically within localisation, we can treat the particles as a belief of the position of a mobile robot.

- Given the timestep $t_0$, we can assume no knowledge of the location of the [[robot]] is known. This can be improved by utilising [[Robot Localisation]].
- We can generate random samples in the environment to model the robot's unknown position:
- ![[Screenshot 2024-03-11 at 20.47.39.png|300]]
- At the timestep $t_1$, we can make an observation. We can then generate weights based on the likelihood the true pose matches the prediction (target).
- ![[Screenshot 2024-03-11 at 20.49.45.png|600]]
- We can then *use* this set of weighted sample to resample the particles. The image below shows this resampling, where the new samples are most prominent where the prior estimate's weights were higher:
- ![[Screenshot 2024-03-11 at 20.51.43.png|300]]
- We can also incorporate the transition model using [[Dead Reckoning]] and propagating the particles' positions according to the movement calculated by dead reckoning.

### Resampling Methods
Above, we do not detail how resampling is performed. There are two main methods:

#### Fitness Proportionate Selection
We can imagine 'buckets' with size equal to the weights of the particles. We can then randomly pick $n$ values such that we return a biased set of random values, dependent on the bucket size.

Analogically, this can be represented as a biased roulette wheel being spun $n$ times:
![[Screenshot 2024-03-11 at 20.58.19.png|300]]

#### Stochastic Universal Sampling
We can instead pick $n$ values at once, at an arc length interval of $\frac{1}{n}$. This minimises variance and is faster:

![[Screenshot 2024-03-11 at 21.14.23.png|300]]