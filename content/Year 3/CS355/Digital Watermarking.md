> Watermarking is the process of modifying an image so that authenticity or tampering can be demonstrated. It is part of [[Forgery Detection]].
> As with [[Image Enhancement]], watermarking can occur in both the [[Spatial Domain Watermarking|pixel domain]] and [[Frequency Domain Watermarking|frequency domain]].

Watermarks can be:
- **Robust** - designed to survive all modifications
- **Fragile** - designed to detect (and be susceptible to) unauthorised modifications.

Also:
- **Visible**
- **Invisible**, specifically such that the watermark is hidden in pixel data.

## Operation
> Watermarking follows the *encoder-decoder* structure.

This means the original image is combined with a signature using an encoder. 
![[Screenshot 2024-02-01 at 17.59.57.png|400]]

The signature can then be extracted using a decoder.
![[Screenshot 2024-02-01 at 18.01.08.png|400]]

If a comparison is necessary, a *comparator* can be used to compare the original signature $S$ and decoded signature $S'$ for a match.
## Applications
### Ownership Claiming
> The owner of an image can embed a *visible* watermark to prevent others from using it. This is most commonly seen in stock image databases.

### Ownership Identification
> The owner of an image can embed an *invisible* watermark, such that, if any other user were to claim ownership, the real owner can prove ownership via the watermark.

### Copy Detection
> The owner of an image can embed unique *invisible* watermarks when sharing the image to distinct users. If a copy is made, the watermark on the copy can be used to determine the user that created the copy.

### Tamper Detection
> If an image is tampered with, the watermarks of the modified image and the original can be compared.