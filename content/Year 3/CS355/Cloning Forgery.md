> Cloning (*or copy-move*) forgery is a type of image forgery, akin to the ones found within [[Compression Forensics]]. It consists of a part of an image being cloned and moved elsewhere in the image.

## Detection
We may consider a few simple methods:
- Use [[Compression Forensics]] to detect changes in compression throughout the image.
- Perform an exhaustive search across the image for similar blocks.

### Exhaustive Searching
> We can iterate in both dimensions, whilst circularly shifting the image and check for duplicate regions (namely, regions that have a similarity value above a determined threshold).

Following this, false positives may exist. As such, we perform:
- **Erosion**, removing negatively matched neighbours.
- **Dilation**, matching unmatched neighbours.
This results in the strongest connections being strengthened and the weak matches being eroded.

We can output the image with the tampered region as bright pixels.

### Pixel Domain Block Matching
> We can use a sliding window and a similarity metric.

In practice, we can use a [[Feature (& Corner) Detection|feature]] extraction algorithm to 'score' a block, then sort these blocks lexicographically.

We can then identify similar blocks as ones that are lexicographically very similar (their difference is below a threshold).

### Frequency Domain Block Matching
We can utilise the [[Cosine Transform]] coefficients and iterate over blocks of coefficients. The general idea is that blocks with very similar frequencies may be cloned.

### Advanced Feature Extraction
> We may also use more advanced methods to characterise [[Feature (& Corner) Detection|features]] in an image, to determine similarity.
#### Local Binary Pattern
> LBP is useful for texture extraction.

We generate a pixel neighbourhood and check the pixel intensities of the neighbourhood. This ensures rotation and scaling invariance.

![[Screenshot 2024-03-04 at 10.46.51.png|400]]

#### Histogram of Oriented Gradients
> We can use [[Gradient Edge Detectors]] as masks to determine gradients in an image (for example, for edge detection).

We can then generate a histogram of the gradient values, with the bins corresponding to the angle of the gradients.