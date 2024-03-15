> This is an [[Image Enhancement]] technique to improve contrast.

We model a cumulative distribution function over the probability of a pixel to be at most a given intensity at a point $x$. In simple terms, we aim to linearise this function, which would result in a near-flat histogram.

![[Screenshot 2024-01-21 at 16.48.50.png]]

This can be done across 1 channel for greyscale images and 3 channels for [[Image Representation#RGB Colour Space|RGB]].

