> Perspective projection is a technique used to project a 3D object onto a 2D plane. Namely, an object and its image.

Essentially, we define a camera matrix which describes this mapping.

From first principles, we have a vector describing the projection in 3D space ($w$ is the scaling factor):
$$p = \begin{bmatrix} x \\ y \\ z \\ w \end{bmatrix}$$
For simplicity, let $w=1$.
Generally, we can derive a transformation matrix which takes into account the centre of the image frame and its distance from the top left corner of the image. Additionally, we introduce a scale factor, resulting in:
$$T = \begin{bmatrix} fk_u & 0 & u_0 & 0 \\ 0 & fk_v & v_0 & 0 \\ 0 & 0 & 1 & 0\end{bmatrix}$$

Generally, the world reference frame does not coincide with the reference frame of the camera. As such, we must use a transformation matrix:
$$F = \begin{bmatrix} r_{11} & r_{12} & r_{13} & t_1 \\ r_{21} & r_{22} & r_{23} & t_2 \\ r_{31} & r_{32} & r_{33} & t_3 \\ 0&0&0&1 \end{bmatrix}$$
Hence, we have the *camera matrix*, defined as:
$$\begin{bmatrix} \lambda x \\ \lambda y \\ \lambda \end{bmatrix} = TF \cdot p$$
