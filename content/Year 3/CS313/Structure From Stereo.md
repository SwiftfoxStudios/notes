> Stereo Vision is the process of gaining depth information in a 2D picture by comparing a scene from two vantage points.

In the example below, we have two cameras, $C_l,C_r$. 

![[Screenshot 2024-01-28 at 16.21.05.png|300]]

Assuming the cameras are at the same $y$ level, we can use similar triangles to form the following equations:
$$
\frac{f}{z} = \frac{u_l}{x} \text{ and } \frac{f}{z} = \frac{-u_r}{b-x}
$$
Hence, we can solve for $z$ and remove the unknown $x$ as:
$$
z = b\frac{f}{u_l-u_r}
$$
