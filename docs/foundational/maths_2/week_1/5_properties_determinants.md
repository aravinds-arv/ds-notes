# Properties of Determinants

In this section we'll take a look at some properties of determinants that could make their computation simplified in some cases:

1. The determinant of the identity matrix \\(\det(I) = 1\\).
2. Swapping two rows/columns of a matrix \\(A\\) reverses the sign of the \\(\det(A)\\). More generally the sign of the determinant is given by \\((-1)^{n} \times \det(A)\\) where an odd number of swaps would result in a -ve sign and an even number in a +ve sign.
3. Determinants behave like a linear function along a row or a column. This means that
    - Multiplying a row/column by a scalar \\(\lambda\\) would also scale the determinant by \\(\lambda\\).
\\[3 . \begin{vmatrix}
1 & 2 \\\\
4 & 5
\end{vmatrix} = \begin{vmatrix}
\mathbf{3} & \mathbf{6} \\\\
4 & 5
\end{vmatrix} = \begin{vmatrix}
1 & \mathbf{6} \\\\
4 & \mathbf{15}
\end{vmatrix} = 3 \times -3 = -9
\\]
    As a consequence of this for an \\(n \times n\\) matrix we also get that \\(\det(\lambda A) = \lambda^{n} \det(A)\\)
    - A determinant of the following form can be expressed as the sum of the determinants obtained by splitting the terms of a single row/column and retaining all the others as the same.
\\[\begin{vmatrix}
a + a' & b + b' \\\\
c & d \\\\
\end{vmatrix} = \begin{vmatrix}
a & b \\\\
c & d \\\\
\end{vmatrix} + \begin{vmatrix}
a' & b' \\\\
c & d \\\\
\end{vmatrix}
\\]

    !!! note

        This however does not mean that \\(\det(A + B) = \det(A) + \det(B)\\). This would be a __wrong interpretation!__

4. If two rows/columns of a matrix \\(A\\) are the same then \\(det(A) = 0\\)
5. Determinants are invariant to elementary row or column operations. In other words adding or subtracting a scalar multiple of a row/column to/from another doesn't change the value of \\(\det(A)\\).
\\[\begin{vmatrix}
3 & 7 \\\\
-2 & 2 \\\\
\end{vmatrix} = \begin{vmatrix}
3 + 0.5(7) & 7 \\\\
-2 + 0.5(2) & 2 \\\\
\end{vmatrix} = \begin{vmatrix}
6.5 & 7 \\\\
-1 & 2 \\\\
\end{vmatrix} = 20
\\]
6. A matrix with one or more rows of zeros will have a determinant of 0.
7. The determinant of an upper triangular matrix (also works for lower) ie., a matrix with all zeros below it's main diagonal is given by the product of it's diagonal elements, also called it's *pivot elements.*
\\[\begin{vmatrix}
\rlap{\kern .24em 1}\raise .04em{\bigcirc} & 2 & 3 \\\\
0 & \rlap{\kern .24em 5}\raise .04em{\bigcirc} & 6 \\\\
0 & 0 & \rlap{\kern .24em 9}\raise .04em{\bigcirc}
\end{vmatrix} = 1 \times 5 \times 9 = 45
\\]
    As we'll see in later weeks, any (invertible) matrix can be reduced into it's corresponding upper triagular form using a method called ***Gauss elimination***. Thus elimination is another way of finding determinants.
8. A non-invertible matrix also known as a ***singular matrix*** has a zero determinant. Conversely a matrix \\(A\\) with \\(\det(A) = 0\\) is singular.
9. If \\(A\\) is non-singular then \\(\det(A^{-1}) = \frac{1}{\det(A)}\\).
10.  The determinant of a matrix product is the product of the individual determinants, \\(\det(AB) = \det(A)\det(B)\\).
11.  Determinants are invariant to transpositions ie., \\(\det(A^T) = \det(A)\\).

## Recommended watches

![type:video](https://www.youtube.com/embed/srxexLishgY)
<br>
![type:video](https://www.youtube.com/embed/23LLB9mNJvc)