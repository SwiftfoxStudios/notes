> MLPs aim to solve the problem with [[Perceptron|single layer perceptrons]] being linearly inseparable. It laid the foundation for image recognition by being able to replicate complex decision boundaries.

## Case Study: XOR Gate
When considering two discrete axes that describes the inputs of a 2-input logic gate, we find that there does not exist a linear function that can separate the outputs of a XOR gate.

Consequently, we find that a [[perceptron]] cannot characterise a XOR gate. This can be disproven by contradiction.

This issue can be solved by adding more layers (*see below*).
![[Screenshot 2024-02-06 at 10.16.50.png|300]]

The outputs of these two perceptrons (which represent NAND & OR) can then be combined with an AND gate to form XOR.