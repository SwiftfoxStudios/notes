> Bayes' Theorem describes the probability of an event, given the probability of a prior.

Namely,
$$
P(A|B)=\frac{P(B|A)P(A)}{P(B)}
$$
Within [[State Estimation]], we can create a simple example to generate a probability space for a robot at a time period (without looking at other time periods).

Given a robot in a 4-room maze with rooms $x=[a,b,c,d]$ with probabilities $P(x)=[0.25,0.25,0.25,0.25]$ (the prior).

We can find the probability that the robot is in a room trivially, with the form:
$$
P(\text{belief}|\text{truth})
$$
Given a sensor with $0.8$ accuracy, such that there is a $0.1$ chance of being in an adjacent room, and given a sensor measurement of the robot being in $b$, we have $P(b|a) = 0.1$.

In reality, we will only have sensor measurements. So given the sensor measurement $b$, using [[Bayes' Theorem]], we can find the probability that the robot is *actually* in $a$ as:

$$
P(a|b) = \frac{P(b|a)P(a)}{P(b)} = \frac{0.1 \cdot 0.25}{P(b)}
$$
As a note here, we don't have $P(b)$, but this can be determined from the [[Law of Total Probability]], as such:

$$
P(b) = \sum_{i=1}^k P(b|x_i)P(x_i) = \sum_{i=1}^k(0.25\cdot0.1,x_b,x_c,x_d)
$$
Hence, if we calculate all of the expectations, we find that $P(a|b) = 0.1$.


