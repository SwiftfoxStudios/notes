> The gradient of pixel values (namely, the partial derivative of pixel intensity along a direction) can be used for edge detection.

There are two main filters which perform this:
- Sobel Edge Detector
- Prewitt Edge Detector

These differ in the magnitude of their masks. The masks (for vertical edge detection) are seen below:
$$
\text{Prewitt}(x_v) = \begin{bmatrix}-1 & 0 & 1 \\ -1 & 0 & 1 \\ -1 & 0 & 1 \\ \end{bmatrix}
$$

$$
\text{Sobel}(x_v) = \begin{bmatrix}-1 & 0 & 1 \\ -2 & 0 & 2 \\ -1 & 0 & 1 \\ \end{bmatrix}
$$
For the horizontal equivalents, the transpose of the above matrices are used.