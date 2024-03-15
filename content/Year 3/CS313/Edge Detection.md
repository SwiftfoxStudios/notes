> An edge feature is a significant local change in the intensity of an image, typically occurring on the boundary between two different regions in an image.

Edges are not necessarily incident to objects. Shadows and rough textures can 'trick' object detection.

A simple method for edge detection is using *local maxima & minima of the first derivative, or x-intercept on a second derivative*. This is, however, susceptible to noise influence (*see below*).

![[Screenshot 2024-01-23 at 15.13.17.png|400]]

## Variants
- [[Gradient Edge Detectors]]
- [[Laplacian Edge Detection]]
- [[Canny Edge Detector]]
