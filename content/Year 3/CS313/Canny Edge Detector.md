> This is a type of [[Edge Detection]] algorithm.

It is a process consisting of multiple steps. Namely,
- Apply [[Spatial Domain Enhancement#Gaussian Filter|Gaussian filter]] to remove noise.
- Find intensity gradients (*for example, by using a [[Gradient Edge Detectors|gradient edge detector]]*).
- Apply non-maximum suppression to thin edges.
- Perform hysteresis

## Hysteresis
For all detected edges, we can set a low threshold and high threshold, resulting in 'weak' and 'strong' edges, respectively.

We can then perform edge linking - this essentially keeps weak edges only if they are adjacent to a strong edge.