# Determinants

Determinants are important concepts in linear algebra. It is used in solving linear systems of equations, testing the invertibility of matrices, finding the eigenvalues & eigenvectors and more. It is only defined for square matrices of the form \\(A^{n \times{n}}\\) and is usually denoted by \\(\det(A)\\) or \\(|A|\\).

> *__Definition__: The determinant of a square matrix \\(A \in \mathbb{R}^{n \times{n}}\\) is a function (of it's entries) that maps \\(A\\) onto a real number.*

Geometrically speaking determinants represent the factor by which a region of space is scaled by a linear transformation (represented by a matrix). For a two dimensional linear transformation this would be the factor by which a plane of unit area gets scaled to ie., either enlarged or shrunk after applying the transformation.

<center>
    <img src="../images/001.png" width=320 hspace=10>
    <img src="../images/002.png" width=300 hspace=10>
</center>

As you can see above the area is scaled by a factor of 6 on applying the linear transformation represented by the matrix. Similarly for 3 dimensions the determinants provide the factor by which volumes are scaled or simply the volume of a 3-dimesional parallelepiped (since we're a scaling up or down from a region of unit volume).

<figure>
    <center>
        <img src="../images/003.png" width=150>
    </center>
    <figcaption>A parellelepiped in 3 dimensions</figcaption>
</figure>

This intuition extends to higher dimensions. *Generally we could say that the determinant of a matrix \\(A\\) represents the signed volume of the n-dimensional parallelepiped formed by the column vectors of \\(A\\)*. The sign of the determinant indicates the orientation of the basis vectors in space. For example in the previous set of images a -ve determinant would swap the positions of the *red* and the *green* basis vectors much similar to flipping a sheet of paper. And a determinant of value 0 would mean all of space has been squished to form a region of lower dimension, a plane in case of 3-d tranformations and a line in case of 2-d tranformations.

## Recommended watch

![type:video](https://www.youtube.com/embed/Ip3X9LOh2dk)