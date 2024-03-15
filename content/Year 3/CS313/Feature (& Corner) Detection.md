> Ideally, a feature detector should accurately and precisely determine points of interest within an image and is repeatable across different images.
>
>**N.B. *feature* and *corner* are typically used interchangeably.**

Features should be:
- Robust against noise and distortion
- Compact

Specifically, we use [[Edge Detection]] as a first step.

Typical methods are:
- [[Harris Corner Detector]]
- [[Scale Invariant Feature Transform]]