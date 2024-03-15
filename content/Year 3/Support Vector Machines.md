> SVMs are a type of supervised [[Machine Learning|learning]] model for data classification. This is split up into two key types.

## Linear SVM
> The linear SVM operates on linearly separable data - where data can be classified on either side of a hyperplane.

The linear SVM generates this hyperplane as a *margin*, defined as:$$w^Tx+b=0$$for the normal to the plane, $w$.
![[Screenshot 2023-11-28 at 20.05.13.png|300]]

This technique, however, is limited to linearly separable data. To extend this, we can use the *kernel trick*.
## Kernel SVM
> This is a method of fitting non linearly separable data onto a hyperplane, using a linear transformation.

The *kernel function* maps a set of points to a point in a new vector space. Using a polynomial kernel as an example, we may have:$$K(x,x')=(1+x^Tx')^d$$
for a polynomial of degree $d$.