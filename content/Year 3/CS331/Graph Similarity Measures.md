> These are the set of solutions for determining the similarity between nodes in a graph.

## Jaccard Similarity
This method is defined as:
$$
J(A,B)= \frac{A \cap B}{A \cup B}
$$
The intuition here is that two nodes are similar if they are pointed to by the same nodes.

Consequently, the limitation here is that only 1 order of ancestor is accounted for, and two nodes with exactly the same structure have identical similarities.

## SimRank
SimRank hopes to solve the above issues with *Jaccard Similarity* by weakening the requirements; two nodes are similar if they are pointed to by *similar* nodes.

As such, it is a recursive similarity measure, with the base case of a node $x$ being most similar to itself (so, $SR(x,x) = 1$).

Hence, we can formulate the recursive formula:
$$
SR(a,b)= \frac{C}{\text{indeg}(a)\cdot\text{indeg}(b)}\sum_{i=1}^{\text{indeg}(a)} \sum_{j=1}^{\text{indeg}(b)}\Biggl( SR \Bigl(\text{in-neighbour}_i(a),\text{in-neighbour}_j(b)\Bigr) \Biggr)
$$
Namely, we recursively pair-wise iterate through every node, setting the SimRank score based on those of their neighbours.


