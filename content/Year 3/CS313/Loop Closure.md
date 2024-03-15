> The **loop closure problem** signifies an issue with [[Mapping]]. It can be solved with some implementations of [[Simultaneous Localisation & Mapping|SLAM]].

Typically, it is difficult to close a loop when building a map. This is due to the [[Signature Matching|feature matching]] accuracy required and the uncertainty in whether a place is familiar to a [[robot]].

This leads to a map possibly being generated that is homotopic to the true environment, but does not account for distance between locations:

![[Screenshot 2024-03-12 at 11.08.27.png]]

In the example above, the left map is generated without a solution to the loop that exists in the true environment (right map).