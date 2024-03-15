> Due to the human vision system's lower acuity for colour differences compared to luminance, images can be encoded by implementing less resolution for [[Chrominance & Luma|chrominance]] information, whilst keeping the luma information fixed.

Consider a ratio:
$$A:b:c$$
Such that we have:
- $A$, the width of the region undergoing subsampling.
- $b$, the number of chroma samples in the first row ($A$) pixels.
- $c$, the number of changes of chroma samples between the first two rows.
## Example

![[Screenshot 2024-01-16 at 11.49.01.png|200]]
The above image has width 4. There are 4 samples in the first row. Looking at each column, we see the chrominance changes for each column.
> Hence, we have the subsampling ratio $4:4:4$.

![[Screenshot 2024-01-16 at 11.52.15.png|200]]
The above image has width 4. There are 4 samples in the first row. Looking at each column, the chrominance *never* changes between the first two rows.
> Hence, we have the ratio $4:4:0$.

To get chrominance values for each pixel after subsampling, we can use a range of averaging methods. Typical ones are:
- Naive Average
- Left (average of leftmost 2 pixels)
- Right (average of rightmost 2 pixels)
- Direct (top-left value)