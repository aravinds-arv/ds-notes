# Computing Determinants

We have explicit explicit expressions to compute the determinants in terms of the elements of a matrix only for \\(1 \times{1}\\) and \\(2 \times{2}\\) matrices. For _n_ = 1,

\\[\det(A) = \det([a_{11}]) = a_{11}\\]

For _n_ = 2,

\\[\det(A) = 
\begin{vmatrix}
a & b \\\\
c & d \\\\
\end{vmatrix}
= ad - bc
\\]

For matrices of higher orders \\(A \in \mathbb{R}^{n \times{n}}\\), we recursively try to reduce the problem of finding the determinant of the \\(n \times{n}\\) matrix to finding the determinant of (\\(n-1) \times(n-1)\\) matrices until the problem gets reduced to computing the determinants of (many) simple \\(2 \times{2}\\) matrices. This algorithm of finding the determinant of any general square matrix is called the *Laplace Expansion.* For a matrix \\(A \in \mathbb{R}^{n \times{n}}\\), Laplace expansion can either be done along rows or along columns:

_1. Expansion along row i_

\\[\det(A) = \sum_{j=1}^{n} (-1)^{(i + j)} a_{ij} \times \det(A_{i,j})\\]

_2. Expansion along column j_

\\[\det(A) = \sum_{i=1}^{n} (-1)^{(i + j)} a_{ij} \times \det(A_{i,j})\\]

Here \\(A_{i,j}\\) is the submatrix of \\(A\\) that is obtained on deleting the \\(i^{th}\\) row and the \\(j^{th}\\) column. The determinant of this matrix \\(\det(A_{i,j})\\) is called the ***minor*** of the term \\(a_{ij}\\) and is usually denoted by \\(M_{i,j}\\). And when the ***minor*** is multiplied by the term \\((-1)^{(i+j)}\\) it's called the ***cofactor*** of \\(a_{ij}\\) denoted by \\(C_{i,j}\\).

## Example
Let us try to compute the determinant of

\\[A =
\begin{vmatrix}
1 & 2 & 3 \\\\
3 & 1 & 2 \\\\
0 & 0 & 1 \\\\
\end{vmatrix}
\\]

Using the Laplace expansion along the first row we get

\\[\det(A) =
(-1)^{(1+1)} . 1\begin{vmatrix}
1 & 2 \\\\
0 & 1 \\\\
\end{vmatrix} +
(-1)^{(1+2)} . 2\begin{vmatrix}
3 & 2 \\\\
0 & 1 \\\\
\end{vmatrix} +
(-1)^{(1+3)} . 3\begin{vmatrix}
3 & 1 \\\\
0 & 0 \\\\
\end{vmatrix}
\\]

Now we can apply the determinant formula for \\(2\times2\\) matrices and obtain the final result

\\[\det(A) = 1(1-0) - 2(3-0) + 3(0-0) = -5\\]