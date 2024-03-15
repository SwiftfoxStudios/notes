>*N.B. This content is identical for CS345 and CS355*
>
> Generally, a Fourier transform is the operation of expressing a waveform (which is not necessarily periodic) as an integral of sines multiplied by a weighting function.

The continuous FT can be defined as:
$$
\Huge \hat{f}(\xi)=\int^\infty_{-\infty}f(x)\cdot e^{-i2\pi\xi x}dx
$$
For most applications, we consider a discrete FT, defined as:
$$
\Huge X_k=\sum^{N-1}_{n=0}x_n\cdot e^{\frac{i2\pi kn}{N}}
$$
For a vector of discrete values $x_n = [x_0,x_1,...,x_{N-1}]$ and $X_k = [X_0,X_1,...,X_{N-1}]$

Specifically, for practical purposes within signal and image processing, it generates a spectrum of values in the frequency domain, given a function in the time domain.

## 2D Discrete Fourier Transform
> The DFT can be extended to two dimensions using the product of two individual DFTs.

For an image $(x,y)$, that is:
$$
\Huge X_k=\sum^{M-1}_{u=0}\sum^{N-1}_{v=0}F(u,v)\cdot e^{i2\pi(\frac{ux}{M}+\frac{vy}{N})}
$$

## Applications
### Breathing Detection
Given a time-domain waveform recording of a room and given some domain knowledge (such as breathing frequency bandwidth, breath wavelength etc.), a Fourier transform could be used to identify breathing by converting the waveform into the frequency domain.
### Gait Analysis
> GA is the analysis of human walking. Theoretically, this is unique to each individual.

We can model the reflections of a signal from body parts of an individual as a time-domain waveform. The frequency of a waveform reflecting from different parts of the body will be different, and as such can be isolated using the transform.
### Image Enhancement
> *see [[Frequency Domain Enhancement]]*
