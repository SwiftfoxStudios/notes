> [[Digital Watermarking]] in the spatial (pixel) domain consists of modifying specific pixel values to embed watermark data.

## Bitplanes
> Using bitplanes are the simplest method of spatial watermarking. It modifies the *least significant bits* (LSB) of binary pixel values. It is fast and can create both visible and invisible watermarks, which are fragile.

Consider a 2x2 grid of pixel values with their binary equivalent:
$$
\begin{bmatrix}56 & 57 \\ 56 & 56 \end{bmatrix} = \begin{bmatrix}00111000 & 00111001 \\ 00111000 & 00111000 \end{bmatrix}
$$
If we use the first LSB, namely the 0$^\text{th}$ bitplane, we have the matrix:
$$
\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix}
$$
To add a watermark to the image, we can *substitute* the pixel values for this specific bitplane with that of a binary watermark, keeping all other layers the same.

![[Screenshot 2024-02-01 at 18.13.58.png|100]]

The intuition is that by modifying the values that have the least influence on the image, the visibility of the watermark is minimised.

For visible watermarks, the bit used can be modified to increase the influence on the overall image. This is seen below:

![[Screenshot 2024-02-01 at 18.12.02.png]]

Likewise, **content-dependent** watermarks can be created, which do not rely on a separate watermark. Rather, the watermark is extracted from the host image. This is done by extracting $N$ random pixel locations from the image and using the 7 most significant bits from the $N$ pixels to form a pixel array of length $7N$.

We can then specify a location to substitute the pixel values with. Visually, the invisibility of the watermark can be optimised by placing the watermark in a location in which the human-visual system is less sensitive to changes:
- Blue channel
- Edge features

