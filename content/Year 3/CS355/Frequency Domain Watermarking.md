> As an alternative to [[Spatial Domain Watermarking]], watermarks can be embedded in the frequency domain spectrum. Typically, this increases robustness (as they are still present after compression or cropping), harder to remove without affecting visual quality and survive low-pass filtering.

There are two main methods:

## LSB Substitution
> Similarly to [[Spatial Domain Watermarking#Bitplanes|SDW]], we can look at a block of data in the DCT basis and modify the frequency intensity values according to our watermark.


This entire process is seen below:

![[Screenshot 2024-02-06 at 13.17.27.png]]

## Spread Spectrum Watermarking
> This utilises a Gaussian distributed watermark.

