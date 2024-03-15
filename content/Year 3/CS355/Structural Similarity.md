> SSIM is a method of determining similarity between two images, based upon [[Chrominance & Luma|luminance]], contrast and structural similarity.

The images are subdivided into regions which are compared against each other.
We can take a weighted product of the three comparison components, such that;
$$SSIM(x,y)=l(x,y)^\alpha \cdot c(x,y)^\beta \cdot s(x,y)^\gamma = \frac{(2\mu_x\mu_y+c_1)(2\sigma_{xy}+c_2)}{(\mu^2_x+\mu^2_y+c_1)(\sigma^2_x+\sigma^2_y+c_2)}$$

## Luminance
> Local luminance is measured by the mean intensity ($\mu_x,\mu_y$) of a region.

As such, this is given by the ratio:
$$l(x,y) = \frac{2\mu_x\mu_y+C_1}{\mu^2_x+\mu^2_y+C_1}$$

## [[Contrast]]
> [[Contrast]] is modelled by the standard deviation of the intensity of a region.

As a high contrast causes a wider spread of the mean pixel intensity, we can use:
$$c(x,y)=\frac{2\sigma_x\sigma_y+c_2}{\sigma^2_x+\sigma^2_y+c_2}$$

## Structure
> The structure of an image can be modelled using [[Pearson Correlation Coefficient|Pearson's r]]:

$$s(x,y)=\frac{\sigma_{xy}+c_3}{\sigma_x\sigma_y+c_3}$$