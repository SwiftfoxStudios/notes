> A black and white image is essentially represented as a matrix of [[Chrominance & Luma|intensity]] values.
> There are different colour models for the representation of *colour* spaces. Namely, [[#RGB Colour Space|RGB]] and [[#Y'CbCr Colour Space|Y'CbCr]].

As such, we represent this as:
$$I(m,n) \in [0,1,...,L-1]$$
for an $x$ bit image s.t. $L= 2^x$. 

Typical colour models for the representation of *colour* spaces are:
## RGB Colour Space
> The RGB model uses a 3-vector (R,G,B) to represent the permutations of these three colour units.
> ![[Screenshot 2024-01-16 at 10.16.24.png|300]]

RGB is device-dependent; it is dependent on a camera's colour filters.

## Y'UV Colour Space
> This model uses a 2-vector (U,V) to represent colour ([[Chrominance & Luma|chrominance]]) and a Y' ([[Chrominance & Luma|luma]]) component to represent intensity.
> ![[Screenshot 2024-01-16 at 11.33.08.png|300]]

Originally, this was done to preserve compatibility between colour and BW television systems.
In the modern day, a variant of this is commonly used, called [[#Y'CbCr Colour Space|Y'CbCr]].
## Y'CbCr Colour Space
> The Y'CbCr model uses a 2-vector (Cb,Cr) to represent colour ([[Chrominance & Luma|chrominance]]) and a Y' component ([[Chrominance & Luma|luma]]) to represent intensity.

This representation can be more useful for representing images, due to the ability to compress the image data without significant loss to quality, via [[Chroma Subsampling|chroma subsampling]].

## Other Representations
### CMYK
> The CMYK is a subtractive model, typically used for printing.

![[Screenshot 2024-01-16 at 16.17.31.png|200]]

### HSL
> HSL uses hue, saturation & luminance to represent colour more intuitively.




