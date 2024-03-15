Forward Error Correction (FEC) are methods of error correction that can locate and often correct editors in transmission. An example is the **Hamming codes**.

We will look at a **(k/n) Block encoder/decoder pair**.
We use a codebook formed of *k-bit* data sequences to *n-bit* codewords such that $n > k$. The **code rate** is defined by $\frac{k}{n} < 1$, and generally characterises the transmission speed.

The example below is a (5,2) code with rate $\frac{2}{5}$.
![[Screenshot 2023-10-10 at 16.51.38.png]]
The goal is to maximise the hamming distance for error correction purposes.

### Error Correction Process
For an example, if the transmitter sends block 00, the receiver should expect 00000. The receiver gets 00100, and as such picks the data block that corresponds to the codeword with the minimum Hamming distance - in this case, 00.