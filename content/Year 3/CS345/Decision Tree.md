> Decision trees are used to draw conclusions from a set of observations.

Essentially, we can generate a binary classifier based on some initial conditions. A key point is that decision trees overfit their classifications; **they have low bias but high variance**.

![[Screenshot 2023-11-29 at 12.12.58.png|300]]

The root of the tree is chosen according to the data's entropy and information gain.

## Attribute Selection (Entropy)
> Entropy is a measure of the variance in uncertainty for an event with given probabilities.

It is defined as:
$$-\sum_{k=1}^{K}p_k \cdot \log_2(p_k)$$
In a decision tree, the aim should be to *minimise* entropy at the leaf nodes.

To do this, we use *information gain* to select the attributes at each stage. We choose the attribute that maximises the information gain, such that the entropy is minimised for all child nodes of a given attribute.

## Random Forests
> Random Forests are said to reduce the problem of overfitting data.

By using a combination of decision trees, each with only a subset of features (attributes) to form a forest of random subsets of features, we can fuse the results to create a better binary classifier.

