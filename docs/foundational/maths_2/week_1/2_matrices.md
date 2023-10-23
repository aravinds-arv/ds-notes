# Matrices

Like vectors, matrices also play a central role in linear algebra. Matrices when paired with vectors can be used to compactly represent _linear systems of equations_ as we'll see in the next lesson. Matrices can also be viewed as _linear transformations_. But before diving into any of these interesting topics let's first formally define what a matrix is and what kind of operations we can perform on it.

> *__Defintion__: A real valued matrix $A$ of order $m\times n$ is an $m\cdot n$ tuple of real elements $a_{ij}$ where $i = 1,2,...,m$ and $j = 1,2,...,n$ and is ordered according to a rectangular scheme consisting of $m$ rows and $n$ columns.*

$$
\left.\left[
\vphantom{\begin{array}{c}1\\1\\1\\1\\1\end{array}}
\smash{\underbrace{
    \begin{array}{cccc}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \cdots & a_{mn} \\
\end{array}
        }_{n\text{ columns}}}
\right]\right\}
\,m\text{ rows}
$$

Vectors are also in a sense, a special case of matrices where the order is either $1\times n$ (row vectors) or $m\times 1$ (column vectors).

## Matrix Operations
Similar to vectors we have certain operations that can be performed on matrices to combine two or more matrices and obtain other matrices. These operations include:

- Matrix Addition
- Matrix Multiplication
- Scalar Multiplication
- Transposition
- Inversion

Let's go over each of these in detail!

### 1. Matrix Addition
The addition of matrices is one of the basic operations that is performed on matrices. Two or more matrices of the same order can be added by adding the corresponding elements of the matrices. If $A = [a_{ij}]$ and $B = [b_{ij}]$ are two matrices of the same order, that is, they have the same number of rows and columns, then the addition of matrices A and B is simply given by $A+B = [a_{ij}] + [b_{ij}] = [a_{ij}+b_{ij}]$.

$$
\scriptsize{
\begin{bmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \cdots & a_{mn} \\
\end{bmatrix} +
\begin{bmatrix}
    b_{11} & b_{12} & \cdots & b_{1n} \\
    b_{21} & b_{22} & \cdots & b_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    b_{m1} & a_{m2} & \cdots & b_{mn} \\
\end{bmatrix} \\
= \begin{bmatrix}
    a_{11} + b_{11} & a_{12} + b_{12} & \cdots & a_{1n} + b_{1n} \\
    a_{21} + b_{21} & a_{22} + b_{22} & \cdots & a_{2n} + b_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} + b_{m1} & a_{m2} + b_{m2} & \cdots & a_{mn} + b_{mn} \\
\end{bmatrix}
}
$$

Matrix addition has the following properties most of which are similar to addition of two numbers:

- **Commutativity**: $A+B=B+A$
- **Associativity**: $A+(B+C)=(A+B)+C$
- **Additive Identity**: $A+0=A=0+A$, here $0$ represents the zero matrix, a matrix filled with zeros in all it's position. When any matrix $A$ is added to $0$, the resultant matrix is $A$ itself
- **Additive Inverse**: $A + {-A}=0=A + {-A}$, where ${-A}$ is the additive inverse of $A$ ie., if $A=[a_{ij}]$, then ${-A}=[{-a_{ij}}]$

### 2. Matrix Multiplication
Unlike addition, multiplication of two matrices is not defined as an element-wise operation, ie., $c_{ij} \neq a_{ij} \times b_{ij}$ [^1] where $c_{ij}$ represents the elements in the product matrix $C=AB$. Instead to compute the elements of the resultant matrix, $C$, we multiply the elements in the rows of $A$ with the elements in the columns of $B$ and take the summation of these products. This can be more clearly understood from the below multiplication of two matrices of order 3 x 3.

$$
\small{
\underbrace{
\begin{bmatrix}
    \mathrm{a} & \mathrm{b} & \mathrm{c} \\
    \mathrm{d} & \mathrm{e} & \mathrm{f} \\
    \mathrm{g} & \mathrm{h} & \mathrm{i} \\
\end{bmatrix}}_{3\times 3} \cdot
\underbrace{
\begin{bmatrix}
    \mathrm{j} & \mathrm{k} & \mathrm{l} \\
    \mathrm{m} & \mathrm{n} & \mathrm{o} \\
    \mathrm{p} & \mathrm{q} & \mathrm{r} \\
\end{bmatrix}}_{3\times 3} =
\underbrace{
\begin{bmatrix}
    \mathrm{(aj + bm + cp)} & \mathrm{(ak + bn cq)} & \mathrm{(al + bo + cr)} \\
    \mathrm{(dj + em + fp)} & \mathrm{(dk + en + fq)} & \mathrm{(dl + eo + fr)} \\
    \mathrm{(gj + hm + ip)} & \mathrm{(gk + hn + iq)} & \mathrm{(gl + ho + ir)} \\
\end{bmatrix}}_{3\times 3}
}
$$

So for obtaining some element $c_{ij}$ we multiply the $i$th row of $A$ with the $j$th column of $B$ and sum them up. This is also termed as the _dot product_ of the corresponding row and column. 

Note that here while we have both $A$ and $B$ of the same order ($3\times 3$), this might not always be the case, sometimes we might need to multiply matrices with different shapes. In such cases matrices can only be multiplied if their neighbouring dimensions match ie., the number of columns in $A$ should be the same as the number of rows in $B$. For instance for two matrices $A_{(m\times k)}$ and $A_{(k\times n)}$, the product $AB$ is possible but the reverse $BA$ is not allowed.

$$
\underbrace{A}_{m\times k}
\underbrace{B}_{k\times n} =
\underbrace{C}_{m\times n}
$$

The resultant matrix $AB$ would thus be of order $m\times n$.

Matrix addition has the following properties:

- **Not Commutative**: $AB\neq BA$
- **Associativity**: $A(BC)=(AB)C$
- **Multiplicative Identity**: $AI=A=IA$, here $I$ represents an _identity matrix_ of suitable order
!!! Example "Identity Matrix"
    An identity matrix of order $n\times x$ is a matrix having $1$'s as it's diagonal entries and $0$'s everywhere else. For instance here's an identity matrix of order $3\times 3$:

    $$
    \begin{bmatrix}
        1 & 0 & 0 \\
        0 & 1 & 0 \\
        0 & 0 & 1 \\
    \end{bmatrix}
    $$

- **Distributivity**: $A(B+C) = AB + AC$

### 3. Scalar Multiplication
Scalar muliplication is the easiest among the matrix operations listed here. Basically for some scalar  $\lambda \in \mathbb{R}$ and some matrix $A$, their product $\lambda A$ simply represents the matrix with each element in $A$ scaled (or multiplied) by the factor $\lambda$.

$$
\lambda
\begin{bmatrix}
    a_{11} & a_{12} \\
    a_{21} & a_{22} \\
\end{bmatrix} =
\begin{bmatrix}
    \lambda a_{11} & \lambda a_{12} \\
    \lambda a_{21} & \lambda a_{22} \\
\end{bmatrix}
$$

The following properties hold for scalar multiplication of matrices:

- Associativity: $\lambda (AB) = (\lambda A)B = A(\lambda B)$
- Distributivity: $\lambda(A + B) = \lambda A + \lambda B$

[^1]: This kind of element-wise multiplication often appears in programming languages when we multiply (multi-dimensional) arrays with each other, and is called a [Hadamard product](https://en.wikipedia.org/wiki/Hadamard_product_(matrices)).

### 4. Transposition
Matrix transposition of finding the transpose of some matrix is an interesting operation. We simply write the rows of the matrix as columns or the columns as rows. For some matrix $A$, we denote it's transpose as $A^T$.

$$
\begin{align}
  A &= \begin{bmatrix}
    1 & 3 \\
    2 & 4 \\
    3 & 5 \\
\end{bmatrix} \\\\
\implies A^T &= \begin{bmatrix}
    1 & 2 & 3 \\
    3 & 4 & 5 \\
\end{bmatrix}  
\end{align}
$$

Notice that each element $a_{ij}$ in $A$ has moved to the position $a_{ji}$ in $A^T$. Also note that while $A$ is a $3\times 2$ matrix, $A^T$ is of order $2\times 3$. 

!!! question "Pause and Ponder"
    What do you think would happen to the order of a square matrix when it is transposed? And what would happen to it's diagonal elements (elements $a_{ij}$ where $i=j$)?

Properties of transposition:

- $(A^T)^T = A$
- $(\lambda A)^T = \lambda A^T$
- $(A + B)^T = A^T + B^T$
- $(AB)^T = B^TA^T$
- If $A=A^T$, then $A$ is said to be symmetric

### 5. Inversion
The inverse of a matrix $A$ is another matrix that when multiplied with $A$ on either side results in an identity matrix. It is denoted as $A^{-1}$, so mathematically we have:

$$
AA^{-1} = A^{-1}A = I
$$

Unfortunately, not all matrices possess an inverse. A matrix is said to be invertible if and only if it is a square matrix and it has a non-zero _[determinant](../week_1/4_determinants.md)_ - a topic that we'll see in a later lesson. And in this lesson we'll not be looking at the general way of computing inverses instead now, we'll look at a simpler way of computing the inverse of a general $2\times 2$ matrix. Consider the below matrix $A$:

$$
A = \begin{bmatrix}
    a & b \\
    c & d \\
\end{bmatrix}
$$

_Suppose we multiply another matrix A' of the form:_

$$
A' = \begin{bmatrix}
    d & -b \\
    -c & a \\
\end{bmatrix}
$$

_then we get_

$$
\begin{align}
    A'A = \begin{bmatrix}
        ad - bc & 0 \\
        0 & ad - bd \\
    \end{bmatrix} &= (ad-bc)I \\\\
    \implies 
    \frac{1}{ad-bc} A' A &= I
\end{align}
$$

_Comparing this equation with $A^{-1}A = 1$, we get_

$$
A^{-1} = \frac{1}{ad-bc}
\begin{bmatrix}
    d & -b \\
    -c & a \\
\end{bmatrix}
$$

Therefore $A^{-1}$ can only exist if $ad-bc \neq 0$, this is what we meant by a non-zero determinant. Matrices that have a non-zero determinant value (and thus invertible) are also termed as _non-singular matrices_, we'll revisit these topics in more detail in upcoming lessons.

## Matrices as Linear Transformation
We saw how we can geometrically represent vectors as arrows with a direction and magitude in the last lesson. But what about matrices? How can we think about them in a geometrically? In a geometric sense, matrices can be viewed as _linear transformations_. Without getting too much into the weeds let's try to develop a brief understanding of this more intuitive picture of matrices (do watch the videos attatched below to get a better idea of this topic).

Matrices can be thought of as functions which takes as input a vector and produces as output another vector. That's why we call this type of an operation a _transformation_, they transform one object to another.

<figure>
    <center>
        <img src="../images/013.svg" width=400>
    </center>
</figure>

So how does a matrix encode the information about how a vector needs to be transformed from one vector from one to another? They do so by recording the position of the _basis vectors_ of a vector space after the transformation.

!!! Example "Basis Vectors"
    Basis vectors are a special set of linearly independent vectors that can be used to represent any other vector within that vector space. The standard basis vectors are considered to be the orthogonal unit vectors. For example for a 2-d vector space, the standard basis would be the unit vector along x-axis, $\begin{bmatrix} 1 \\ 0 \\ \end{bmatrix}$ and the unit vector along y-axis, $\begin{bmatrix} 0 \\ 1 \\ \end{bmatrix}$:

    <figure>
        <center>
            <img src="../images/014.svg" width=350>
        </center>
    </figure>

Let's try to visualize a 2-d tranformation to get a better hold of this idea. If we think about the 2-d vector space as a Cartesian plane with grid lines spaced by unit length, then here's what a linear transformation would look like:

<figure>
    <center>
        <img src="../images/015.webp" width=450>
    </center>
</figure>

Now if had initially had some vector say $v=\begin{bmatrix} -1 \\ 2 \\ \end{bmatrix}$, that was initially described as a linear combination of the standard basis vectors ie., $v = -1i + 2j$, then after the tranformation we can get the position of the tranformed vector $Lv$ by simply taking the same linear combination of the new basis vectors.

<figure>
    <center>
        <img src="../images/016.webp" width=450>
    </center>
</figure>

> In case you noticed, yes the transformation shown in the previous animation is not the same as the one  above (because I didn't create it, 3b1b did!), but still I hope you get the idea. 

The only information we need to preserve in a matrix to retrieve any vector in the transformed vector space is the transformed basis vectors and that's precisely what the columns of a matrix represent. In the above transformation, we have the transformed bases as:

$$
\begin{align}
    L(i) = \begin{bmatrix}
        1 \\ -2 \\
    \end{bmatrix} \quad
    L(j) = \begin{bmatrix}
        3 \\ 0 \\
    \end{bmatrix}
\end{align}
$$

Now using these 4 numbers how can we get the transformed version of $v$? We simply multiply the matrix having these transformed bases as it's columns with $v$ (the order of multiplication here should by _matrix $\times$ vector_):

$$
\begin{bmatrix}
1 & 3 \\
-2 & 0 \\
\end{bmatrix}
\begin{bmatrix}
    -1 \\ 2 \\
\end{bmatrix} = 
\begin{bmatrix}
    5 \\ 2 \\
\end{bmatrix}
$$

Isn't that beautiful, with just 4 numbers we can now tell us where any vector in a vector space would land after a transformation. Now whenever we encounter a matrix we should learn to immediately associate it with it's geometric picture - a transformation of vector space.

If you didn't quite understand the idea of linear transformation now, don't worry, this intuition behind matrices though helpful if learnt (and taught) earlier, is not necessarily needed to understand the topics ahead (atleast upto week 3). We'll formally be introduced to topics like vector spaces, basis vectors etc. around week 4. _And once you have a good idea of these topics you can revisit this lesson and try to connect the dots._

## Recommended Watches
![type:video](https://www.youtube.com/embed/kYB8IZa5AuE)
<br>
![type:video](https://www.youtube.com/embed/XkY2DOUCWMU)
<br>
![type:video](https://www.youtube.com/embed/J7DzL2_Na80)
<br>
![type:video](https://www.youtube.com/embed/FX4C-JpTFgY)
