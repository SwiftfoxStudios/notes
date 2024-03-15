> [[Image Compression]] has two main forensic applications.

## Double Compression
> This indicates if an image has been compressed multiple times. This may not be down to forgery, and can be accidental.

Following [[Image Compression#Quantisation|quantisation]], we can represent the values of the [[Cosine Transform|DCT]] coefficients in a histogram. This histogram will be normally distributed, with ranges based on the quantisation factor. 

For single compression (with factor 3), we may have:
![[Screenshot 2024-02-23 at 15.10.17.png|400]]

If the image is quantised again, with a different factor, periodic peaks or empty bins may be present:
![[Screenshot 2024-02-23 at 15.12.59.png|400]]
![[Screenshot 2024-02-23 at 15.14.20.png|400]]

## JPEG Ghost
> JPEG Ghosts can be used to identify forged images and localise the forged regions.

We utilise the properties of double compression, namely that when considering the *Sum of Squared Differences* between the original unquantised image and the quantised image (following dequantisation), eg:
$$
\textbf{q}_{2}  [3,8,6] \to 2[2,4,3] = [4,8,6]
$$
Hence, $\text{SSD} = 1^2 + 0 + 0 =1$,

We have that an image quantised by the same (or a multiple of the other) factor have a difference in SSD of 0.

For a general image, in the pixel domain, we can calculate the quantisation error (averaged across the three colour channels) after compression at quality $Q$ as such:
$$
d(x,y,q)
= \frac{1}{3}\sum^3_{i=1}\Bigl(f(x,y,i)-f_Q(x,y,i)\Bigr)^2
$$
The difference image is first spatially averaged across a b × b pixel region and normalised to account for fluctuations in frequency differences across the image. Hence, we have:
$$
\delta(x,y,q)
= \frac{1}{3}\sum^3_{i=1}
\frac{1}{b^2}
\sum_{b_x=0}^{b-1}
\sum_{b_y=0}^{b-1}
\Bigl(f(x+b_x,y+b_y,i)-f_Q(x+b_x,y+b_y,i)\Bigr)^2
$$
