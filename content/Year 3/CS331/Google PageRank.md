> The **PageRank** algorithm achieves a measure of each node in a graph's relative importance (degree centrality). It is similar to the [[Hyperlink Induced Topic Search]] algorithm.

It is based on the intuition that a node is more important if it has a higher in-degree (additionally, with incident nodes being more important) than other nodes.

PageRank can be given by the simplified formula:
$$

PR(v) = \sum_{x \in \text{indeg}(v)}\frac{PR(x)}{|\text{outdeg}(x)|}
$$
With this simplified expression, there are two main issues:
- A node $x$ with $\text{indeg(x)} = 0$ has $PR(x) = 0$.
- A set of nodes that form a cycle accumulate PageRank score.

We modify the algorithm to allow for the possibility of a 'random hop' with probability $c$, which prevents this:
$$
PR(v) = c\cdot\Biggl(\sum_{x \in \text{indeg}(v)}\frac{PR(x)}{|\text{outdeg}(x)|}\Biggr)
+
(1-c)\frac{1}{|V|}
$$
