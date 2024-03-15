> Compression is the process of reducing the number of bits required to represent data.

We can utilise the compression of an image (and its resulting loss in image quality) for forensic use. (*See: [[Compression Forensics]]*)

We define the *compression ratio* as the ratio between the number of bits in the original ($c_1$) and compressed ($c_2$) images.
$$c_r = \frac{c_1}{c_2}$$

We can define the *redundancy* (a measure of the size of the difference in bits) as:
$$
r_d = 1-\frac{1}{c_r}
$$

Generally, there are three types of redundancy solved by compression:
- **Spatial** (correlations exist between neighbouring pixels) - solved via *transform mapping*
- **Psychovisual** (limitations in the HVS, typically manifested in the frequency domain) - solved via *quantisation*.
- **Coding** (using more bits per pixel than needed) - solved via *entropy coding*.

## JPEG
JPEG is a standard for image compression. It is comprised of the following steps:

### Color Space Conversion
We convert from RGB to YCbCr. We can then perform [[Chroma Subsampling]].

### Division Into Subimages
To reduce computational complexity, we split the image into blocks.

### Discrete Cosine Transform
We perform the [[Cosine Transform]] on the image to convert it into the frequency domain. Generally, we find that most of the relevant data (low frequency) lies in a small subsection of the resulting matrix.

### Quantisation
After converting to the frequency domain, we can use a quantisation matrix which will prioritise low frequencies in the frequency spectrum. 

We divide the DCT matrix by the quantisation matrix, then round to an integer. The result will typically be one with the higher frequency values being 0. 

Values representing lower frequencies appear in the top left of the matrix; as such, we store the quantised values by traversing the trailing diagonal as below:

![[Screenshot 2024-02-22 at 17.59.31.png|300]]

This stage of the compression process is usually the stage most detectable in [[Compression Forensics]] due to the lossy nature of this step.
### Huffman Coding
> *Main Page: [[Huffman Coding]]* does not exist yet.

We can remove coding redundancy via *Huffman coding*. Essentially, we can assign binary codewords to intensity values via a probability mass function, based on their frequency of occurrence in the image. Huffman codes are of variable length and uniquely decodable.

The idea is that longer codewords will be assigned to values that occur less.