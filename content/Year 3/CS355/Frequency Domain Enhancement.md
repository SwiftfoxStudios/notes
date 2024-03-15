> This approach utilises a wave transform, to convert between the spatial domain and frequency domain, in order to reduce noise in a specific frequency.

There are two main approaches:
- [[Fourier Transform]]
- [[Cosine Transform]]
Converting to the frequency domain results in a frequency spectrum. Typically, most noise appears in the *high-frequency* channels. Hence, we can use a mask to reduce noise at a specific frequency.

## Simple Mask
> We can design a simple mask centred around the origin of a frequency spectrum, which preserves all of the given frequency information below a given threshold.

Some examples are seen below.

![[Screenshot 2024-01-30 at 10.33.27.png|300]]

## Ideal Low Pass Filter
> The [[#Simple Mask]] can be extended to a low pass filter, which is a circle with radius $r$, centred around the origin of the frequency spectrum.

![[Screenshot 2024-02-01 at 18.21.02.png|100]]
## Gaussian Low Pass Filter
> The GLP Filter extends the [[#Ideal Low Pass Filter]] by using a [[Gaussian Distribution]] as a noise model. This means the least noisy frequencies are kept, with a decreasing influence as the frequency increases.

![[Screenshot 2024-02-01 at 18.24.23.png|100]]

## Butterworth Low Pass Filter
> This is similar to the [[#Gaussian Low Pass Filter]], with a parameter $n$ controlling the steepness of the cut-off range. It can result in a wider low pass space.

The equation for this relationship is:
$$
\Huge\frac{1}{1+(\frac{D(u,v)}{D_0})^{2n}}
$$

![[Screenshot 2024-02-01 at 18.25.58.png|100]]

## High Pass Filter
> Any low pass filter can be inverted to create a high pass filter.

## Notch Filter
> Notch filters are used to remove repeated (pattern) spectral noise from an image.