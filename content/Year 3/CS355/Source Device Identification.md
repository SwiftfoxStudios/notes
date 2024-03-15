> This is the process of identifying the source device of an image.

## Simple Methods
- [[Chroma Subsampling]] can be used if the subsampling method is known and are distinct for the set of possible devices.
- The EXIF header, which stores image metadata, can be used if the image is still in its original format.
- Some cameras have [[Digital Watermarking]] technology built in.

## Sensor Pattern Noise
> Imperfections of [[Imaging Sensor|image sensors]] are an example of a possible device signature. They can survive image processing (such as [[Image Compression]]). It is deterministic.

### Fixed Pattern Noise
This is the variation in light sensitivity when the pixel array is not subjected to light. This can be easily mitigated by subtracting a dark image from the original. **Most cameras do this already.**

### Photo Response Non-Uniformity
- **Pixel Non-Uniformity** arises due to the variation in sensitivity per pixel due to manufacturing defects (in silicon).
- **Low Frequency Defects** arise due to light refraction and adjacent sensor interference.


## Aside: Shot Noise
> Shot Noise is visibly random noise which arises due to variations in the number of incident photons to the pixel array.