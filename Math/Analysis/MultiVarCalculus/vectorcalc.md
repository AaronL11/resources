\newpage

# Vector Calculus

Vector calculus studies **Vector Valued Functions**. These are functions that permit input of vectors representing multiple variables.

This is paired with the **Gradient** or **Del** operator $(\nabla)$ which takes a function and returns a vector of partial derivatives:
$$
\nabla f =
\begin{bmatrix}
    \partial f\over\partial x_1\\
    \partial f\over\partial x_2\\
    \vdots\\
    \partial f\over\partial x_n\\
\end{bmatrix}
$$

## Connection between Calculus and Linear Algebra

This hints towards a deeper and more nuanced connection between linear algebra and calculus. We already know that the derivative operator is linear. If we take the time to look back at abstract vector spaces we may notice that the derivative forms a linear operator over the vector space of functions:
$$
{d\over dx}(af(x)+bg(x)+ch(x))
$$
We also know that linear functions can have derivatives. And every linear transformation (or function) can be represented as a matrix transformation. From that reasoning it seems to make sense that we should be able to take the derivative of a matrix transformation. All we need to do is write it in terms of a differentiable linear function.

This entire chapter focuses on the connection between linear algebra and calculus. So there is plenty more to be said and more details to work out.

### Derivative of the Dot Product

Let's try to take the function $f(\vec{x})$ that represents the dot product of $\vec{x}$ with $\vec{a}$:
$$
f(\vec{x}) = \vec{a}\cdot\vec{x}
$$
Let's take the gradient vector of $f$. To do this we only need to write the dot product as a sum of components:
$$
f(\vec{x}) = \sum_i^na_ix_i
$$
Then we form a vector of all the partial derivatives. Since each component undergoes the same transformation we can simply go ahead and calculate one:
$$
{\partial f\over\partial x_i} = a_i
$$
This gives us with the following expression for the gradient of the dot product:
$$
\nabla(\vec{a}\cdot\vec{x}) =
\begin{bmatrix}
    a_1\\a_2\\\vdots\\a_n
\end{bmatrix}=\vec{a}
$$
This is analogous to the how derivatives work in scalar valued functions:
$$
{d\over dx}(ax) = a
$$

### Derivative of a Matrix Transformation

Let's expand on this and take the simple transformation $A\vec{x}$
$$
\begin{bmatrix}
    a&b\\c&d
\end{bmatrix}
\begin{bmatrix}
    x\\y
\end{bmatrix}
=
\begin{bmatrix}
    ax+by\\
    cx+dy
\end{bmatrix}
$$
We can write our final result as two functions in terms of $x$ and $y$:
$$
\begin{bmatrix}
    f_1(x,y)\\
    f_2(x,y)
\end{bmatrix}
$$

We then define our matrix derivative like so:
$$
{d\over dx}A(\vec{x}) =
\begin{bmatrix}
    {\partial f_1\over\partial x}&{\partial f_1\over\partial y}\\
    {\partial f_2\over\partial x}&{\partial f_2\over\partial y}
\end{bmatrix}
$$
So the derivative of this matrix transform is just $A$ again:
$$
{d\over d\vec{x}}A(\vec{x})
$$

### Another Example

Let's try a more interesting example by examining a the linear transformation:
$$
f(\vec{x}) = \vec{x}^TA\vec{x}
$$
Where $A$ is an $n\times n$ matrix and $\vec{x}$ is an $n\times 1$ vector.

For simplicity we will assume that $n=2$. We can write out the matrix product like so:
$$
\begin{bmatrix}
    x&y
\end{bmatrix}
\begin{bmatrix}
    a&b\\c&d
\end{bmatrix}
\begin{bmatrix}
    x\\y
\end{bmatrix}
=
\begin{bmatrix}
    x&y
\end{bmatrix}
\begin{bmatrix}
    ax+by\\cx+dy
\end{bmatrix}
$$
This gives us the following quadratic form:
$$
\vec{x}^TA\vec{x} = ax^2+(b+c)xy+dy^2
$$
And so to get the gradient we simply form a vector of the partial derivatives:
$$
\nabla\left(\vec{x}^TA\vec{x}\right) =
\begin{bmatrix}
    2ax+(b+c)y\\
    (b+c)x+2dy
\end{bmatrix}
$$
Which can be expressed as another linear transformation:
$$
\begin{bmatrix}
    2a&b+c\\
    b+c&2d
\end{bmatrix}
\begin{bmatrix}
    x\\y
\end{bmatrix}
$$
However notice that we could decompose the matrix as:
$$
\begin{bmatrix}
    2a&b+c\\
    b+c&2d
\end{bmatrix}
=
\begin{bmatrix}
    a&b\\
    c&d
\end{bmatrix}
+
\begin{bmatrix}
    a&c\\
    b&d
\end{bmatrix}
$$
Which is simply our original $A$ and it's transpose:
$$
\nabla\left(\vec{x}^TA\vec{x}\right) = \left(A+A^T\right)\vec{x}
$$
For a *symmetric* matrix $A^T=A$ we also have:
$$
\nabla\left(\vec{x}^TA\vec{x}\right) = 2A\vec{x}
$$
Which forms a matrix analog of ${d\over dx}ax^2 = 2ax$. At least for $2\times2$ matrices $A$. However this expression still holds for the $n\times n$ case.

This method is particularly useful for calculating the gradient of a long equation in multiple variables:
$$
f(x) = 2x^2+3xy+5y^2+zy-2xy
$$
Which has the quadratic form:
$$
\begin{bmatrix}
    x&y&z
\end{bmatrix}
\begin{bmatrix}
    2&3&0\\
    0&5&1\\
    -2&0&0
\end{bmatrix}
\begin{bmatrix}
    x\\y\\z
\end{bmatrix}
$$
So we can easily find the derivative by doing $\left(A+A^T\right)\vec{x}$:
$$
\begin{bmatrix}
    4&3&-2\\
    3&10&1\\
    -2&1&0
\end{bmatrix}
\begin{bmatrix}
    x\\y\\z
\end{bmatrix}
=
\begin{bmatrix}
    4x+3y-2z\\3x+10y+z\\y-2x
\end{bmatrix}
=
\nabla f(\vec{x})
$$

## Vector and Scalar Fields

There are a few ways we can graph these.

## Vector Valued Functions

### Conservative Functions


## Divergence

## Curl

## Jacobian

Let's look at the map of some arbitrary function:

PICTURE

If you recall our original intution for slopes in calculus, we looked at a tiny region near our curve. In this region the curve appeared linear. This built the concept of our derivative through limits.

Let's try the same approach on our 2D map:

PICTURE

If you notice this forms a small region that looks linear.

If we treat this like a linear mapping then we can think of our new basis as being constructed of these small infinitesimal pieces. These pieces essentially explain the changes of the coordinates in our original function. Does that description sound familiar? If it does, then you'd notice that this would mean the components of our matrix are **Derivatives**.

$$
\begin{bmatrix}
    {\partial f_1\over\partial x}&{\partial f_1\over\partial y}\\
    {\partial f_2\over\partial x}&{\partial f_2\over\partial y}
\end{bmatrix}
$$

### Jacobian Matrix

This is called the **Jacobian Matrix**.

If $f$ is a function from $\mathbb{R}^n$ to $\mathbb{R}^m$ denoted by:
$$
\boldsymbol{f} =
\begin{bmatrix}
    f_1(x_1,..,x_n)\\
    \vdots\\
    f_m(x_1,..,x_n)
\end{bmatrix}
$$
Then the jacobian of $f$ is:
$$
\bold{J}=
\begin{bmatrix}
    {\partial f_1\over\partial x_1}&\cdots&{\partial f_1\over\partial x_n}\\
    \vdots&&\vdots\\
    {\partial f_m\over\partial x_1}&\cdots&{\partial f_m\over\partial x_n}
\end{bmatrix}
$$

### Jacobian Determinant

If $n=m$ then the jacobian matrix is *square*. This allows us to take a determinant. Like with normal matrix theory, if this determinant is non-zero then the jacobian can be inverted.
