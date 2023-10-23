# Vectors

### Why Linear Algebra?
Linear Algebra is a field of mathematics that could be said to lie in the intersection of many different engineering domains some of which include, but not limited to data science, structural engineering, image processing, linear programming, fluid mechanics, control theory, network flow & engineering design. Many of these areas of science and engineering require numerical methods, and linear algebra provides the vast majority of these numerical tools. 

But why is this the case?, what makes this specific domain of mathematics ***so versatile***? Well to put it simply we could say that linear algebra is the most easiest and most practical language we can use to convey data about real world to computers so that they can process large amounts of data and provide us with useful insights. 

Finally speaking in the context of data science, it is quite universally accepted that a solid grasp of the concepts in linear algebra lays foundation for a deeper understanding of data science and ML algorithms. As we'll see in later courses, many of these so called _algorithms_ are indeed powered by methods from linear algebra behind the scenes. [^1]

[^1]: If you'd like to get a better idea about how different concepts in linear algebra is used in data science and machine learning _[click here](https://www.freecodecamp.org/news/how-machine-learning-leverages-linear-algebra-to-optimize-model-trainingwhy-you-should-learn-the-fundamentals-of-linear-algebra/)_

## Vectors
As we said above, linear algebra evolved as way of reliably conveying information about the real world in a language that computers can easily understand and _vectors_ could be thought of as the symbols or alphabets that make up this language. In a broader sense there are atleast three different ways to think about vectors:

- Vectors as an array of numbers - The computer science perspective
- Vectors as an arrow with a magnitude and direction - The physics perspective
- And vectors as objects that can added together or scaled or both - The mathematics perspective

For our purposes, we'll most often be using the mathematics (or numerical) view of vectors because this view generalizes both of the other views, saying that a vector can be anything where there’s a sensible notion of adding two objects or scaling an object by some factor to produce another object of the same kind. From this mathematical point of view anything that satisfies these two properties can be considered as a vector. Here are some examples of such vector objects:

- Geometric vectors: This example of a vector may be familiar from highschool physics. What defines a geometric vector is its length and the direction it’s pointing, but as long as those two facts are the same you can move it around and it’s still the same vector. Physical quanities like velocity, displacement and force are represented using geometric vectors.

<figure>
    <center>
        <img src="../images/004.svg" width=300>
    </center>
</figure>

- Polynomials: Polynomials are also vectors, two polynomials can be added together which result in another polynomial and they can be  multiplied by a scalar to give a polynomial as well. Therefore, polynomials are (rather unusual) instances of vectors.

<figure>
    <center>
        <img src="../images/005.png" width=350>
    </center>
</figure>

- Audio Signals: Audio signals are vectors, they are represented as a series of numbers. We can add audio signals together, and their sum is a new audio signal. If we scale an audio signal, we also get an audio signal. Therefore, audio signals are a type of vector too.
- Elements of $\mathbb{R}^n$: This is the type of vectors that we'll primarily focus on. Elements of $\mathbb{R}^n$ are tuples or arrays of $n$ real numbers written vertically with square brackets around them. For example:-

$$
a = \begin{bmatrix}
    -2 \\
    3 \\
\end{bmatrix} \in \mathbb{R}^2
$$

This is a vector in 2-dimensions since is has two components -2 and 3. Geometrically we represent it as an arrow in cartesian plane with it's tail sitting at the origin and it's tip at the coordinates $(-2, 3)$.

<figure>
    <center>
        <img src="../images/006.svg" width=450>
    </center>
</figure>

!!! note
    Keep in mind that the coordinate $(-2,3) \neq \begin{bmatrix} -2 \\ 3 \\ \end{bmatrix}$. The former is an indicator of position in space while the latter represents a real mathematical object.

This geometric intuition of a vector could be extended to higher dimension as well (though we may not really be able to visualize 4-d space or beyond), for example consider a vector in 3-d space $a = \begin{bmatrix} 2 \\ 1 \\ 3 \end{bmatrix}$.

<figure>
    <center>
        <img src="../images/007.png" width=450>
    </center>
</figure>

The first number $2$ tells you how far to move along the x-axis, the second number $1$ tells you how far to move parallel to the y-axis and the third number $3$ tells you how far to move parallel to the z-axis.

## Vector Operations
We said earlier that any object that can be added to another or scaled by some factor to produce another object of the same kind could be called as a vector. Pretty much every linear algebra topic revolves around these two fundamental operations of vector addition and scalar multiplication. Now that we have a good idea of what a vector is both numerically and geometrically let's look at how we can perform these fundamental operations on them.

### Vector Addition
To add two vectors we simply take the sum of their corresponding components. Here's an example:

$$
\begin{bmatrix}
    1 \\
    2 \\
\end{bmatrix} + 
\begin{bmatrix}
    3 \\
    -1 \\
\end{bmatrix} =
\begin{bmatrix}
    1 + 3 \\
    2 - 1 \\
\end{bmatrix} = 
\begin{bmatrix}
    4 \\
    1 \\
\end{bmatrix}
$$

How do we represent this geometrically? To obtain the sum of two vectors in space, we move the first vector so that it's tail sits on the tip of the second vector and then join the tail of the first vector to the tip of the second:

<center>
    <img src="../images/008.svg" width=320 hspace=5>
    <img src="../images/009.svg" width=320 hspace=5>
</center>

### Scalar Multiplication
A scalar is just a number or a factor by which we scale any given vector, such an operation is called scalar multiplication. To perform scalar multiplication, we again simply multiply each component by the number or scalar. Example:

$$
2 \times \begin{bmatrix}
    3 \\
    1 \\
\end{bmatrix} =
\begin{bmatrix}
    6 \\
    2 \\
\end{bmatrix}
$$

And geometrically this would literally just mean to scale or extend the vector by the given factor:

<figure>
    <center>
        <img src="../images/010.svg" width=320>
    </center>
</figure>

In case the factor that is multiplies is either between $0$ and $1$ or is less than $0$ then, the vector is squished down or flipped around and extended in the opposite direction

<center>
    <img src="../images/011.svg" width=320 hspace=5>
    <img src="../images/012.svg" width=320 hspace=5>
</center>

To get a better idea of the geometric intuitions behind these vector operations and why they work so, I'd highly recommend you to watch the [3Blue1Brown](https://www.youtube.com/3blue1brown) video in the recommended watch section below.

## Recommended Watch
![type:video](https://www.youtube.com/embed/fNk_zzaMoSs)