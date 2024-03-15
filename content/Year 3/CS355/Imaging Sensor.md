> This is the process of forming an image using an *image sensor*.
## Array
The imaging sensor is made up of a sensor array, formed of 1 sensor per pixel in the array.
There are two major types, [[CMOS]] and [[CCD]] sensors.
## Sampling
> Whilst the object is in a continuous space, the image requires *discretisation* to be represented. This is **sampling**.

The *spatial resolution* defines the number of pixels per unit of measurement. As such, this is defined by the density of the sensor array.

In practice, sampling is performed by defining some discrete $comb(t)$ function, such that:
$$f(t)\cdot comb(t)$$
Results in the discretisation of the continuous function, $f(t)$ representing the image.

## Quantisation
> This is the process of intensity undergoing *discretisation*, rather than the pixel space (as with sampling).

![[Screenshot 2024-01-11 at 17.20.11.png|300]]
For example, in the image above, we note the decreasing number of discrete sets for a given continuous intensity space.

