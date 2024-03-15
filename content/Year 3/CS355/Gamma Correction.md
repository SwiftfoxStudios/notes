> Whilst cameras follow a linear relationship between object luminance and the perceived pixel intensity, this is not true for humans. GC accounts for this and modifies the pixel intensities.

Given the corrected output intensity $v_{out}$ and recorded object luminance $v^\gamma$, we can modify each bit of the range of pixel intensities such that (*for an $n$-bit image*):

$$v_{out} = 2^n \cdot (\frac{v}{2^n})\gamma$$
![[Screenshot 2024-01-11 at 17.43.15.png|400]]
