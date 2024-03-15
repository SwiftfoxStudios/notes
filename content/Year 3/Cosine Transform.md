> The DCT is similar to the [[Fourier Transform#2D Discrete Fourier Transform|Fourier transform]], but uses only cosines. This means it only handles real coefficients.

For a 2D image $f(x,y)$ of size $M \times N$, this would be:
$$
\Huge F(u,v) = \sum^{M-1}_{x=0} \sum^{N-1}_{y=0}f(x,y)\alpha(u)\alpha(v)\cos\Bigl(\frac{\pi (2x+1) u}{2M}    \Bigr)\cos\Bigl(\frac{\pi (2y+1) v}{2N}    \Bigr)
$$

The DCT is particularly useful for image compression, as we can remove coefficients with small frequency values without severely impacting image clarity.