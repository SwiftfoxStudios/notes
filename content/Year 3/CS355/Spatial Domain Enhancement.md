> SDE is an [[Image Enhancement]] technique where the pixel intensity values themselves are changed as needed. *For the purposes of our knowledge, we will assume the images are greyscale.*

> N.B Contrast Enhancement is CS355 only, whereas all other content is shared with CS313

## Contrast Enhancement
> We can utilise histograms which plot the number of pixels at the same grey level within an image.

A high [[contrast]] image will have a large spread of pixel intensities (*see [[Contrast]]*).
As such, we can utilise *[[Histogram Equalisation]]* to increase an image's contrast.

## Smoothing
> Pixel values are averaged according to a mask of neighbouring pixels.
> This is also a method of removing Gaussian noise.

Smoothing will remove some noise, at the cost of adding blur to an image.

## Median Filter
> The Median filter takes the median of neighbouring pixel values as the corresponding pixel value.

Whilst [[#Smoothing]] is not edge-preserving due to blur (*which is useful for [[Edge Detection]]*), the MF often is. Likewise, smoothing does not remove outliers within the pixel data.

## Gaussian Filter
> Pixel values are modified according to a Gaussian filter, which priorities neighbouring pixels.

This relationship in one dimension is characterised by the Gaussian with standard deviation $\sigma$:
$$
\Huge g(x) = \frac{1}{\sqrt{2\pi}\sigma}e^\frac{-x^2}{2\sigma^2}
$$
In two dimensions, we can take the product of two Gaussians:
$$
\Huge g(x,y) = \frac{1}{2\pi\sigma^2}e^\frac{-x^2+y^2}{2\sigma^2}
$$
## Convolutions
> *Further information: [[Convolution]]*