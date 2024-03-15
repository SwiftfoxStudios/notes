> **HITS** is a [[Google PageRank]]-like ranking algorithm.

The intuition is that a node is more important if:
- It has out-neighbours which are important.
- It has in-neighbours which are important.

We define the scores for each node:
- **Authority**, $a_x$: dependent on the in-neighbours having a good **hub** score.
- **Hub**, $h_x$: dependent on the out-neighbours having a good **authority** score.

We can then iteratively modify these scores until a stable set has been reached.