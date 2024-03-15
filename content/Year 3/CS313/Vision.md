> Robots typically use an [[Imaging Sensor|image sensor]] (which may be part of a camera) to acquire and [[Image Representation|represent]] images.

Colour can be perceived using a [[Colour Filter Array]].
Colour (*in terms of vision*) is typically represented as [[Image Representation#RGB Colour Space|RGB]], [[Image Representation#CMYK|CMYK]] or [[Image Representation#HSL|HSL]].
## Resolution Reduction
Typically, for implementations within robotics, the resolution of images is reduced in order to reduce memory usage whilst preserving information.

A common implementation of this is reducing the colour space to a single vector (greyscale) or even binary (black/white pixels).

## Image Formation
> When using a camera, we can model how the image is formed on a screen, in relation to the object itself.

The simplest model is the [[Pinhole Camera Model]].

In geometrical terms, we can represent the relationship between an object and its image, as produced by a camera, essentially projecting a 3D image onto a 2D plane. This is done using [[Perspective Projection]]. This however, causes the image to lose depth information.

We can recover depth information in two ways:
- [[Structure From Stereo]]
- [[Structure From Motion]]

## Image Enhancement
> *see [[Image Enhancement]]*

