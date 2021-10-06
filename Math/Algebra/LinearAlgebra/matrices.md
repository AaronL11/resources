\newpage

# Matrices

## Matrices as Systems of Linear Equations

Notice how when we were solving these linear equations we didn't really need the $x$, $y$, and $z$ variables. We only were working with their coefficients and so long as we sort of centered them properly then solving them because a lot easier.

For example take the following system of 3 equations in 3 variables:
$$
\begin{aligned}
    x+ 3y -2z\\
    y-z\\
    3x+y
\end{aligned}
$$
For simplicity we can write the coefficients in a nice form like this with the columns representing the positions of our $x$, $y$, and $z$ variables:
$$
\begin{bmatrix}
    1&3&-2\\
    0&1&-1\\
    3&1&0
\end{bmatrix}
$$
This structure is called a **Matrix**. The *matrix* (meaning womb in latin) holds all of our coefficients and makes it easy for us to work through solving systems of linear equations.

Matrices can also be represented with the following index notation:
$$
A = a_{ij}
$$
where $i$ is each row and $j$ is each column.

### Matrix Size

Matrices come in all sorts of shapes and sizes, however they all have a nimber of rows and a number of columns. We represent this as the matrix belonging to the set $M_{mn}$, where $m$ is the number of rows and $n$ is the number of columns.

For example: here are those linear equations from the first section again as matrices:
$$
\begin{aligned}
M_{22} &\ni
\begin{bmatrix}
    4&3\\
    7&-2
\end{bmatrix}
\qquad
M_{32} \ni
\begin{bmatrix}
    4&5\\
    5&-6\\
    -2&-4
\end{bmatrix}\\
M_{56} &\ni
\begin{bmatrix}
    1&-8&7&-2&3&4\\
    5&2&5&1&7&-8\\
    3&-5&2&4&3&1\\
    2&-4&3&-2&2&-3\\
    6&1&8&-9&2&-4\\
\end{bmatrix}
\end{aligned}
$$

### Matrix Addition and Subtraction

Now it's time to think about what it means to perform our basic arithmetic operations on matrices, starting with subtraction.

Matrix addition happens element wise:
$$
A+B = (a_{ij}+b_{ij})_{ij} = c_{ij} = C
$$
The best way to understand this is to simply ask, what does it mean to add two linear equations?
$$
ax + bx = (a+b)x
$$

For example:
$$
\begin{bmatrix}
    1&2\\3&4
\end{bmatrix}
+
\begin{bmatrix}
    5&6\\7&8
\end{bmatrix}
=
\begin{bmatrix}
    6&8\\10&12
\end{bmatrix}
$$
Addition is essentially done over the elements of our field, which means that we also have a matrix full of the additive identity element, which would interact with $A$ as follows:
$$
\boldsymbol{0}_{mn} + A = A + \boldsymbol{0}_{mn} = A,\quad\forall A\in M_{mn}
$$
where $\boldsymbol{0}_{mn}$ is the $m\times n$ matrix of all zeros:
$$
\boldsymbol{0}_{mn} =
\begin{bmatrix}
    0&\cdots&0\\
    \vdots&\ddots&\vdots\\
    0&\cdots&0
\end{bmatrix}
$$

### Matrix Scaling

Matrix scaling happens element wise as well:
$$
kA = (ka_{ij})_{ij}
$$

For example:
$$
5
\begin{bmatrix}
    1&2\\3&4
\end{bmatrix}
=
\begin{bmatrix}
    5&10\\15&20
\end{bmatrix}
$$

Matrix scaling is distributive over matrix addition for the same reasons:
$$
k(A+B) = kA + kB
$$
This is because any multiplication operations on sums of linear systems of equations are linear:
$$
4
\begin{pmatrix}
    2x+3y\\
    -x+y
\end{pmatrix}
+5
\begin{pmatrix}
    -2x-4y\\
    x-2y
\end{pmatrix}
=
\begin{aligned}
    (4\cdot2-5\cdot2)x+(4\cdot3-5\cdot4)y\\
    (-4+5)x+(4-5\cdot2)y\\
\end{aligned}
$$
We would also have scaling by the multiplicative identity in our field:
$$
1A = A
$$
As this value would leave the elements in the matrix unchanged.

### Matrices and Vector Spaces

If you noticed, as I've gone through how we can go about adding matrices, these properties all satisfy the axioms of a vector space.

This means we can express linear combinations of matrices as belonging to a span of a subspace of matrices:
$$
aA + bB = \text{span}_\mathbb{F}\{A,B\}
$$
We could define a basis to center these operations around.

For example, all $2\times2$ real matrices can be expressed as belonging to the vector space $M_{22}(\mathbb{R})$ with a basis:
$$
\begin{bmatrix}
    a&b\\c&d
\end{bmatrix}
\in
\text{span}_\mathbb{R}
\left\{
\begin{bmatrix}
    1&0\\0&0
\end{bmatrix},
\begin{bmatrix}
    0&1\\0&0
\end{bmatrix},
\begin{bmatrix}
    0&0\\1&0
\end{bmatrix},
\begin{bmatrix}
    0&0\\0&1
\end{bmatrix}
\right\}
$$

### Matrix Products

We're going to discuss Matrix Multiplication really briefly now.

$$
AB = \sum_{i=0}^nA_iB_i
$$

Multiplying a matrix by another one simply applies the left matrix to each column in the right matrix:
$$
A
\begin{bmatrix}
    \big|&\big|&&\big|\\
    b_1&b_2&\cdots&b_n\\
    \big|&\big|&&\big|
\end{bmatrix}
=
\begin{bmatrix}
    \big|&\big|&&\big|\\
    Ab_1&Ab_2&\cdots&Ab_n\\
    \big|&\big|&&\big|
\end{bmatrix}
$$

We could also consider an inverse matrix $B$ such that:
$$
BA = I
$$
We would usually denote this matrix as $A^{-1}$:

Since matrix multiplication is not commutative, we need to build the idea of a right inverse $AA^{-1}$ and a left inverse $A^{-1}A$:

This all ties back in to linear equations in a striking way. We can represent a system of linear equations as a **matrix multiplication**. For example take the system:
$$
\begin{aligned}
    &a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n &= y_1\\
    &a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n &= y_2\\
    &\qquad\qquad\quad\vdots &\quad \vdots\\
    &a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n &= y_m
\end{aligned}
$$
Now write it as the matrix product:
$$
\begin{bmatrix}
    a_{11}&a_{12}&\cdots&a_{1n}\\
    a_{21}&a_{22}&\cdots&a_{2n}\\
    \vdots&\vdots&\ddots&\vdots\\
    a_{m1}&a_{m2}&\cdots&a_{mn}
\end{bmatrix}
\begin{bmatrix}
    x_1\\x_2\\\vdots\\x_n
\end{bmatrix}
=
\begin{bmatrix}
    y_1\\y_2\\\vdots\\y_m
\end{bmatrix}
$$
Or more compactly as:
$$
A\vec{x} = \vec{y}
$$
This would mean that our system of equations has a unique solution **if and only if** $A$ is invertible:
$$
\begin{aligned}
    A\vec{x} &= \vec{y}\\
    A^{-1}A\vec{x} &= A^{-1}\vec{y}\\
    I\vec{x} &= A^{-1}\vec{y}\\
    \vec{x} &= A^{-1}\vec{y}
\end{aligned}
$$
But how can we determine if a matrix is invertible?? One of the big keys is something we've already discussed in the linear equations section, which is **determinants**.

## Determinants

$\det A$ or $|A|$.

$$
\begin{vmatrix}
    a&b\\c&d
\end{vmatrix}
=ad-bc
$$

### Leibniz Formula

### Laplace's Formula

This is

### Minors

### Adjoint Matrix

An adjoint matrix is a matrix who

## Similar Matrices

Similar Matrices are matrices

The associated *space* of solutions that each matrix represents is the same, since the system of equations of both matrices represent the same relationship.

Symbolically this relationship looks like:
$$
A\sim D \iff \exists P: PA=D \land A = P^{-1}D
$$

### Matrix Transpose

$\left(A_{ij}\right)^T = A_{ji}$

$$
\begin{bmatrix}
    1&2\\3&5
\end{bmatrix}^T
=
\begin{bmatrix}
    1&3\\2&5
\end{bmatrix}
$$

$$
(AB)^T = B^TA^T
$$

Complex matrices come with an additional operation, the **conjugate transpose** $\left(A^T\right)^*=A^\dagger$:
$$
\begin{bmatrix}
    1+i&-i\\
    3+4i&2-3i
\end{bmatrix}^\dagger
=
\begin{bmatrix}
    1-i&3-4i\\
    i&2+3i
\end{bmatrix}
$$


## Useful Matrix Forms

### Row Echelon Form

$$
\begin{bmatrix}
    a&*&\cdots&*\\
    0&b&*&\vdots\\
    \vdots&&\ddots&\vdots\\
    0&0&\cdots&z
\end{bmatrix}
$$

Echelon is a french term for 

### Reduced Row Echelon Form

The Reduced Row Echelon Form is exactly what it sounds like, the matrix is reduced so that the first non-zero entry to every row is 1. These are called our leading ones and every entry above or below a leading one is zero

$$
\begin{bmatrix}
    1&0&\cdots&0&*\\
    0&1&0&\vdots&\\
    \vdots&&\ddots&\vdots&\\
    0&0&\cdots&1&*
\end{bmatrix}
$$
Remember how this applies to our solutions for linear equations. Essentially the system of equations given by the matrix has a solution if and only if that matrix is similar to the identity matrix.
$$
Ax = y
$$
Can only be solved for a unique $x$ if there exists a $A^{-1}$ so that:
$$
x = A^{-1}y
$$
So what the RREF tells us, is not only whether or not a system of linear equations has a solution, but also the number of linearly independent variables in our inputs. Recall the portion about infinite solutions. When we solved that system and found a paramaterized form for our variables, we essentially put our matrix into RREF only to find that it's RREF was no identical to the identity matrix. If you recall that system was inconsistent and had no general inverse system, just like the matrix representing that system would not have an associated inverse.

Putting a matrix into RREF is pretty simple, you essentially just want to put the matrix into REF with every leading term being one, then you simply subtract from the lowest leading one until all entries that are above leading ones are zero.
<!-- $$
\begin{bmatrix}
    
\end{bmatrix}
$$ -->


### Column Echelon Form

There is also a column echelon form and reduced column echelon form.

To put a matrix into CEF we simply perform row operations over the *columns* of a matrix rather than it's rows. This however is equivalent to performin row operations over the matrix's transpose.

For all invertible matrices, their RREF and RCEF should be the same.

## Matrix Properties

### Dimension

### Row and Column Space

If we go back to the relationship between matrices and systems of equations, we can remember that we can represent a linear system of equations as belonging to a subspace:
$$
\begin{aligned}
    2x+y+3z\\
    3x-2y-z\\
    -x+2z
\end{aligned}
=
\begin{pmatrix}
    p\\q\\r
\end{pmatrix}
\in
\text{span}
\left\{
\begin{pmatrix}
    2\\3\\-1
\end{pmatrix},
\begin{pmatrix}
    1\\-2\\0
\end{pmatrix},
\begin{pmatrix}
    3\\-1\\2
\end{pmatrix}
\right\}
$$
But remember that the coefficients of our linear system of equations can also be represented as matrix $A$:
$$
A=
\begin{bmatrix}
    2&1&3\\
    3&-2&-1\\
    -1&0&2
\end{bmatrix}
$$

This means that the matrix $A$ has the vectors in the spanning set as it's columns.

This is called the **column space** of $A$, denoted $\text{col}(A)$.

Likewise the column space of it's transpose is the **row space** of $A$, denoted $\text{row}(A)$.

For example, take the following matrix
$$
\begin{bmatrix}
    a&b&c&d\\
    e&f&g&h\\
    i&j&k&l\\
\end{bmatrix}
$$

The column space is simply the set spanned by the columns of our matrix as vectors:
$$
\text{col}(A)
=
\text{span}
\left\{
    \begin{bmatrix}
        a\\e\\t
    \end{bmatrix}
    ,
    \begin{bmatrix}
        b\\f\\j
    \end{bmatrix}
    ,
    \begin{bmatrix}
        c\\h\\k
    \end{bmatrix}
    ,
    \begin{bmatrix}
        d\\h\\l
    \end{bmatrix}
\right\}
$$
The row space is the set of vectors spanned by the rows of our matrix
$$
\text{row}(A)
=
\text{span}
\left\{
    \begin{bmatrix}
        a\\b\\c\\d
    \end{bmatrix}
    ,
    \begin{bmatrix}
        e\\f\\g\\h
    \end{bmatrix}
    ,
    \begin{bmatrix}
        i\\j\\k\\l
    \end{bmatrix}
\right\}
=
\text{col}\left(A^T\right)
$$

### Rank and Linear Independence

So we've already shown how we can describe the columns of a matrix as a spanning set of vectors. Know we also know that not all spanning sets are linearly independent.

If we think about what it would mean to find out if our vectors were linearly independent we can imagine we start off with a set of linearly independent vectors $\beta$.
$$
\beta=
\begin{bmatrix}
    \big|&\big|&&\big|\\
    b_1&b_2&\cdots&b_n\\
    \big|&\big|&&\big|
\end{bmatrix}
$$
If a set of vectors is linearly dependent it would mean that at least *one* of these vectors is a linear combination of the others. If we think about this in terms of matrix multiplication, we are really just taking this linearly dependent set and multiplying it by the matrix
$$
\begin{bmatrix}
    1&0&\cdots&0&a\\
    0&1&&0&b\\
    \vdots&&\ddots&\vdots\\
    0&0&\cdots&1&z
\end{bmatrix}
\beta
=
\begin{bmatrix}
    \big|&&\big|&\big|&&\big|\\
    b_1&\cdots&b_n&ab_1+&\cdots&+zb_n\\
    \big|&&\big|&\big|&&\big|
\end{bmatrix}
$$
Where the final row is some linear combination of our linearly independent vectors.

So to determine the linear independence of our vectors we would want to be able to show that our matrix is equivalent to multiplying a linearly independent set by the identity.

This seem like a job for row operations, and if you recall, the RREF form of a matrix essentially tells us the number of linearly independent variables. So in this case all we actually have to do is put $\beta$ into RREF where we're considering our variables as some basis.

*Yet another reason why RREF is very important.*

We call the number of linearly independent vectors the **rank** of the matrix. This is because that is the number of vectors that form the basis of our column space. The basis of our column space is also called the the image of $A$, $\text{Im}(A)$. And if you remember that the dimension of a subspace is the number of linearly independent vectors in that subspace; then finding the rank is essentially like asking for the dimension of the image:
$$
\text{rank}(A) = \text{dim}\big(\text{Im}(A)\big)
$$

### Kernel (Null Space) and Nullity

The nullspace of 

$$
A\vec{x} = \vec{0}
$$


$$
\begin{aligned}
    A\vec{x} &= -A\vec{y}\\
    A\vec{z} &= 3A\vec{w}
\end{aligned}
$$
$$
\begin{aligned}
    A(\vec{x}+\vec{y}) &= \vec{0}\\
    A(\vec{z}-3\vec{w}) &= \vec{0}
\end{aligned}
$$
So we can build

The dimension of the matrix kernel is called the nullity.
$$
\text{nullity}(A) = \dim\big(\ker(A)\big)
$$

You might want to think about how this relates to the kernel of a linear transformation as well.

### Rank-Nullity Theorem

Let's think about how we can relate the image, kernel, rank and nullity together.

Let's imagine anaylizing the following set of vectors:
$$
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        2\\0\\3\\-2
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\5\\3\\4
    \end{bmatrix}
    ,
    \begin{bmatrix}
        -6\\5\\-6\\10
    \end{bmatrix}
    ,
    \begin{bmatrix}
        4\\-5\\3\\-8
    \end{bmatrix}
    ,
\end{Bmatrix}
$$
This represents the column space of the matrix:
$$
\begin{bmatrix}
    2&0&-6&4\\
    0&5&5&-5\\
    3&3&-6&3\\
    -2&4&10&-8
\end{bmatrix}
$$
It's RREF looks like:
$$
\begin{bmatrix}
    1&0&-3&2\\
    0&1&1&-1\\
    0&0&0&0\\
    0&0&0&0
\end{bmatrix}
$$
If we were to discuss this matrix in terms of it's column space, the RREF is essentially telling us that a span of 4 vectors has 2 linearly independent vectors, this means we can form two vectors that cancel out from the linearly dependent vectors just as we've shown when discussing how the kernel works. And 2 linearly independent vectors plus 2 linearly dependent vectors is 4 four total vectors, which is how many vectors are in our column space.

This is call the **rank-nullity theorem** and is states that the dimension of a matrix is the sum of it's rank and it's nullity:
$$
\text{rank}(A) + \text{nullity}(A) = n
$$

In essence all the rank-nullity theorem is stating is simply the number of linearly independent vectors plus the number of linearly dependent vectors gives us the total vector in our column space.

## Types of Matrices

This next section will be discussing a variety of matrix types that are often useful. This is meant to be as comprehensive as possible so it can be used a resource for future use.

### Augmented Matrices

An augmented matrix is formed when we concatenate two matrices and separate them with a line like so:
$$
\left[A|B\right]
$$

Any row operations we do on one side we simply apply to the other side as well.
$$
\begin{bmatrix}
    1&0&0&\big|&3&4&1\\
    0&1&0&\big|&-1&0&2\\
    0&0&1&\big|&3&-2&1\\
\end{bmatrix}
$$
$$
\begin{bmatrix}
    2&0&1&\big|&9&6&3\\
    0&-1&2&\big|&7&-4&0\\
    -3&-1&2&\big|&16&8&3\\
\end{bmatrix}
$$
So we started with some matrices $[A|B]$ and we ended up with matrices $[C|D]$. Since $A$ was our identity matrix this means that our final row reductions is equivalent to multiplying $CI$. And since we did the exact same operations on the right side then that means that $D=CB$.

So when we write $[A|B]$ and we multiply $A$ by some matrix $P$, we are also simultaniously multiplying $B$ by that matrix as well.

To illustrate this, think of the augmented matrix representing the relation:
$$
A = BC
$$
and whatever we do to $A$ we also do through $P$ so we end up with:
$$
PA = PBC
$$
We can also say that our new augmented matrix represents the relation:
$$
E = DC
$$

This comes in handy if we want to find the inverse of a matrix, we simply set $B$ to the identity matrix and row reduce $A$ to the identity.

Take the matrix:
$$
A =
\begin{bmatrix}
    2&0&-4&\\
    1&1&4&\\
    5&1&-3&
\end{bmatrix}
$$
And now we're going to row reduce
$$
\begin{bmatrix}
    2&0&-4&\big|&1&0&0\\
    1&1&4&\big|&0&1&0\\
    5&1&-3&\big|&0&0&1
\end{bmatrix}
{\huge\rightarrow}
\begin{bmatrix}
    1&0&0&\big|&-{7\over2}&-2&2\\
    0&1&0&\big|&{23\over2}&7&-6\\
    0&0&1&\big|&-2&-1&1
\end{bmatrix}
$$
Let's investigate this a little, remember that we're representing the relation:
$$
A = IC
$$
in this case $C=A$, and when we apply our row reductions it is the equivalent to left multiplying by $P$:
$$
PA = PIC
$$
and since we've shown on the left hand side that $PA=I$ then $P=A^{-1}$ and the right hand represents the matrix $PI=A^{-1}$.

Say you want to solve the system:
$$
Ax=y
$$
We can write $[A|y]$ and if we row reduce $A$ to the identity it is equivalent to applying the inverse to $y$ to get:
$$
x = A^{-1}y
$$

### Elementary Matrices and Similar Matrices

This gives rise to expressing row reductions as matrix multiplications.

1. Multiplying a row by another just means we want to form a linear combination of two rows:
    $$
    \begin{bmatrix}
        1&0&\cdots&0&0&\cdots&0\\
        0&1&\\
        \vdots&&\ddots&&&&\vdots\\
        0&0&\cdots&1&a&\cdots&0\\
        0&0&\cdots&0&1&\cdots&0\\
        \vdots&&\vdots&&&\ddots&\vdots\\
        0&0&\cdots&0&0&\cdots&1
    \end{bmatrix}
    $$
2. Swapping two rows just means that we swap the ones associated with that row.
    $$
    \begin{bmatrix}
        1&0&\cdots&0&0&\cdots&0\\
        0&1&\\
        \vdots&&\ddots&&&&\vdots\\
        0&0&\cdots&0&1&\cdots&0\\
        0&0&\cdots&1&0&\cdots&0\\
        \vdots&&\vdots&&&\ddots&\vdots\\
        0&0&\cdots&0&0&\cdots&1
    \end{bmatrix}
    $$
3. Scaling a row just means we change the one to whatever coefficient we're scaling by:
    $$
    \begin{bmatrix}
        1&0&\cdots&0&0&\cdots&0\\
        0&1&\\
        \vdots&&\ddots&&&&\vdots\\
        0&0&\cdots&a&0&\cdots&0\\
        0&0&\cdots&0&1&\cdots&0\\
        \vdots&&\vdots&&&\ddots&\vdots\\
        0&0&\cdots&0&0&\cdots&1
    \end{bmatrix}
    $$

Two matrices $A$ and $B$ are said to be **similar** $A\cong B$ if there is a product of invertible elementary matrices such that:
$$
\prod_i^kE_iA = B
$$

### Diagonal Matrices

A **Diagonal Matrix** is a matrix where all the entries are zero except for the main diagonal. These matrices are square matrices
$$
\begin{bmatrix}
    *&0&&0\\
    0&*&&\vdots\\
    &&\ddots\\
    0&\cdots&&*
\end{bmatrix}
$$

One of the benefits to a diagonal matrix is that it's determinant is simply the product of the diagonal entries:
$$
\det
\begin{vmatrix}
    2&0&0\\
    0&3&0\\
    0&0&5
\end{vmatrix}
=
2*3*5 = 30
$$

### Triangular Matrices

A **lower** triangular matrix has zeros above the diagonal with entries below.
$$
\begin{bmatrix}
    *&0&\cdots&0\\
    *&*&&\vdots\\
    &&\ddots\\
    *&\cdots&&*
\end{bmatrix}
$$

An **upper** triangular matrix is zero below the main diagonal with entreis above.
$$
\begin{bmatrix}
    *&*&\cdots&*\\
    0&*&&\vdots\\
    &&\ddots\\
    0&\cdots&&*
\end{bmatrix}
$$

Like diagonal matrices, one of the benefits to a triangular matrix is that the determinant is the product of the diagonal entries:
$$
\det
\begin{vmatrix}
    2&1&4\\
    0&3&-6\\
    0&0&1
\end{vmatrix}
=2*3*1=6
$$

### Hessenberg Matrices

A **Hessenberg Matrix** looks like a triangular matrix but with less values.

An **upper** hessenberg matrix is zero except for the diagonal and a few entries in the subdiagonal.
$$
\begin{bmatrix}
    *&*&\cdots&*\\
    *&*&&\vdots\\
    &&\ddots\\
    0&\cdots&&*
\end{bmatrix}
$$
A **lower** hessenberg matrix is zero except for the diagonal and a few entries in the superdiagonal.
$$
\begin{bmatrix}
    *&*&\cdots&0\\
    *&*&&\vdots\\
    &&\ddots\\
    *&\cdots&&*
\end{bmatrix}
$$

### Tridiagonal Matrices

A matrix that is both an upper and lower hessenberg matrix is called **tridiagonal**. A tridiagonal matrix looks like:
$$
\begin{bmatrix}
    *&*&0&0&\cdots&0\\
    *&*&*&0&&\vdots\\
    0&*&*&*&&\vdots\\
    0&0&*&*&&\vdots\\
    \vdots&&&&\ddots\\
    0&\cdots&\cdots&\cdots&\cdots&*
\end{bmatrix}
$$

### Sparse Matrix

A **Sparse Matrix** is a matrix where most of the elements are zero.

$$
\begin{bmatrix}
    *&0&0&\cdots&0\\
    0&*&*&&\\
    *&0&\ddots&&\vdots\\
    \vdots&&&0\\
    0&&\cdots&*&0\\
\end{bmatrix}
$$

These matrices are great for storage in computers.

We won't see too many Hessenberg, Tridiagonal, or Sparse matrices right now as but they come in handy in the more advanced sections.

### Symmetric Matrices

A **Symmetric Matrix** is an $n\times n$ square matrix $A$ that is equal to it's own transpose $A = A^T$

For example, take the matrix:
$$
\begin{bmatrix}
    1&1&3\\
    1&2&5\\
    3&5&3
\end{bmatrix}
$$

### Hermetian Matrix

A **Hermetian Matrix** is an $n\times n$ square matrix $A$ with complex entries that is equal to it's own conjugate transpose $A = A^\dagger$, denoted $A=A^H$ sometimes as well.

For example, take the matrix:
$$
\begin{bmatrix}
    1&-i&3+2i\\\\
    i&2&5-6i\\\\
    3-2i&5+6i&3
\end{bmatrix}
$$

### Normal Matrices

Normal matrices are matrices that commute with their conjugate transpose:
$$
AA^\dagger = A^\dagger A
$$

### Orthogonal Matrices

**Orthogonal Matrices** are $n\times n$ square matrices who's transpose is equal to their inverse.
$$
A^TA = AA^T = I
$$
Note, since the conjugate transpose of a real matrix is it's transpose, this means that real orthogonal matrices are also normal matrices.

The reason why this works is because orthogonal Matrices are made up of columns of orthogonormal vectors:
$$
A
=
\begin{bmatrix}
    \big|&\big|&&\big|\\
    a_1&a_2&\cdots&a_n\\
    \big|&\big|&&\big|
\end{bmatrix}
$$
So multiplying by it's transpose creates a matrix of all the dot products:
$$
A^TA = a_i^Ta_j
$$
Since the columns are orthonormal all dot products will be zero unless $a_i=a_j$ then the dot product equals itself, then it's one.

### Unitary Matrices

A matrix who's conjugate transpose is equal to it's inverse is called **unitary**.
$$
AA^\dagger = A^\dagger A = I
$$
Since the conjugate transpose for real matrices is just the transpose then all orthogonal real matrices are unitary. Additionally, since unitary matrices commute with their conjugate transpose they are also normal.

### Involutory Matrices

An involuntory matrix is a matrix that is also an involution (it's own inverse):
$$
A = A^{-1}
$$
This means that even powers of $A$ are the identity:
$$
A^{2n} = I,\quad \forall n\in\mathbb{Z}
$$
And odd powers are just $A$

For example, take the matrix:
$$
\begin{bmatrix}
    0&1\\1&0
\end{bmatrix}
$$
if we multiply this matrix with itself we get the identity:
$$
\begin{bmatrix}
    0&1\\1&0
\end{bmatrix}
\begin{bmatrix}
    0&1\\1&0
\end{bmatrix}
=
\begin{bmatrix}
    1&0\\0&1
\end{bmatrix}
$$

### Householder Matrix

A **Householder Matrix** is an involutory matrix that is both unitary and hermitian.
$$
\begin{aligned}
    A&=A^\dagger\\
    AA^\dagger = A^\dagger A &= I\\
    A^2 &= I
\end{aligned}
$$
These matrices arise from the **householder transform**, which you'll see much much much later when we cover numerical linear algebra and optimizations for solving matrix problems.

## Matrices as Linear Transformations

Let $T:P_3\rightarrow M_{22}$ act on a basis for $P_3$ as follows:

$$
\begin{aligned}
T\left(
x^3
\right)
&=
\begin{bmatrix}
    3&0\\2&0
\end{bmatrix}
&\quad
T\left(
x^2
\right)
=
\begin{bmatrix}
    0&1\\1&0
\end{bmatrix}
\\
T\left(
x
\right)
&=
\begin{bmatrix}
    0&0\\0&3
\end{bmatrix}
&\quad
T\left(
1
\right)
=
\begin{bmatrix}
    1&-3\\0&-2
\end{bmatrix}
\end{aligned}
$$
Now let's say we want to know how this transformation act on any individual polynomial.
$$
T\left(ax^3+bx^2+cx+d\right) = 
\begin{bmatrix}
    p&q\\r&s
\end{bmatrix}
$$
Well by the property of linearity:
$$
aT\left(x^3\right)+bT\left(x^2\right)+cT\left(x\right)+dT\left(1\right)=
\begin{bmatrix}
    p&q\\r&s
\end{bmatrix}
$$
Now by subbing in our matrices:
$$
\begin{aligned}
a
\begin{bmatrix}
    3&0\\2&0
\end{bmatrix}
+
b
\begin{bmatrix}
    0&1\\1&0
\end{bmatrix}
+
c
\begin{bmatrix}
    0&0\\0&3
\end{bmatrix}
+
d
\begin{bmatrix}
    1&-3\\0&-2
\end{bmatrix}
&=
\begin{bmatrix}
    3a+d&b-3d\\2a+b&3c-2d
\end{bmatrix}\\
&=
\begin{bmatrix}
    p&q\\r&s
\end{bmatrix}
\end{aligned}
$$
This forms a system of linear equations:
$$
\begin{aligned}
    3a-d&=p\\
    b-3d&=q\\
    2x+b&=r\\
    3c-2d&=s
\end{aligned}
$$
And anytime we have a sytem of linear equations we have a matrix for the coefficients.
$$
\begin{bmatrix}
    3&0&0&-1\\
    0&1&0&-3\\
    2&-1&0&0\\
    0&0&3&-2
\end{bmatrix}
\begin{bmatrix}
    a\\b\\c\\d
\end{bmatrix}
=
\begin{bmatrix}
    p\\q\\r\\s
\end{bmatrix}
$$
Notice that $T$ can be represented as this matrix multiplication $Ax=y$ where $A\in M_{44}$ and $x,y\in\mathbb{R}^4$

As we have found, we can represent the linear transformation $T$ as this $4\times4$ matrix $A$.

### Relation to Span

Now if you notice, the polynomial $ax^3+bx^2+cx+d$ is actually $\text{span}\{x^3,x^2,x,1\}$. So in essence what we've done is show the matrix $A$ represents $T$'s action on the span of our basis. And the new matrix $\begin{bmatrix}p&q\\r&s\end{bmatrix}$ is some combination of $\left\{\begin{bmatrix}3&0\\2&0\end{bmatrix},\begin{bmatrix}0&1\\-1&0\end{bmatrix},\begin{bmatrix}0&0\\0&3\end{bmatrix},\begin{bmatrix}-3&-1\\0&-2\end{bmatrix}\right\}$.

Now what's interesting here is that the columns of our matrix $A$, look awfully familiar. If we take our matrices as vectors in $\mathbb{R}^4$ notice we get the basis:
$$
\left\{\begin{bmatrix}3\\0\\2\\0\end{bmatrix},\begin{bmatrix}0\\1\\-1\\0\end{bmatrix},\begin{bmatrix}0\\0\\0\\3\end{bmatrix},\begin{bmatrix}-3\\-1\\0\\-2\end{bmatrix}\right\}
$$
Which is the $\text{col}(A)$.

### Linear Transformations as Systems of Linear Equations

This has the added bonus of saying that linear transformations between vector spaces are actually a system of linear equations from **one basis** to **another**. With the unknowns or *inputs*, belonging to the basis of our *domain*, and the *outputs* belonging to the basis codomain.

Since matrices really represent the coefficients of a system of equations, then all of our linear transformations from on vector space to another have some matrix representation in terms of how they act on our initial basis.

### Non-Standard Basis

Now this is all well and good, however we've forgotten to think about what would happen if we had a non-standard basis. Since we can think about our basis $\left\{x^3,x^2,x,1\right\}$ as:
$$
\begin{bmatrix}
    1&0&0&0\\
    0&1&0&0\\
    0&0&1&0\\
    0&0&0&1
\end{bmatrix}
\begin{bmatrix}
    x^3\\x^2\\x\\1
\end{bmatrix}
$$

Let's say our starting basis was $\left\{x^3+x^2,x^3-x,x^3+1\right\}$. This can be represented as an endomorphism $T:P_3\rightarrow P_3$ via the following matrix:
$$
\begin{bmatrix}
    1&1&0&0\\
    1&0&-1&0\\
    1&0&0&1
\end{bmatrix}
\begin{bmatrix}
    x^3\\x^2\\x\\1
\end{bmatrix}
=
\begin{bmatrix}
    x^3+x^2\\x^3-x\\x^3+1
\end{bmatrix}
$$
Notice this also acts like a transformation $F:\mathbb{R}^4\rightarrow\mathbb{R}^3$.

Now let's say we have the following transformation $Q:P_3\rightarrow M_{22}$
$$
\begin{aligned}
Q\left(x^3+x^2\right)=
\begin{bmatrix}
    1&0\\2&0
\end{bmatrix}
\quad Q\left(x^3+x\right)=
\begin{bmatrix}
    0&-3\\0&3
\end{bmatrix}
\\
Q\left(x^3+1\right)=
\begin{bmatrix}
    7&0\\2&-5
\end{bmatrix}
\end{aligned}
$$
If look at how $Q$ acts on our span:
$$
Q\left(a\left(x^3+x^2\right)+b\left(x^3-x\right)+c\left(x^3+1\right)\right)
$$
this can be represented as the following transformation:
$$
\begin{bmatrix}
    1&0&7\\
    0&-3&0\\
    2&0&1\\
    0&3&-5
\end{bmatrix}
\begin{bmatrix}
   a\\b\\c
\end{bmatrix}
$$
and we alredy know that out vector $\begin{bmatrix}a\\b\\c\end{bmatrix}$ can be written as a transformation from our standard basis in $P_3$. $px^3+qx^2+rx+s$
$$
\begin{bmatrix}
    1&0&7\\
    0&-3&0\\
    2&0&1\\
    0&3&-5
\end{bmatrix}
\begin{bmatrix}
    1&1&0&0\\
    1&0&-1&0\\
    1&0&0&1
\end{bmatrix}
\begin{bmatrix}
    p\\q\\r\\s
\end{bmatrix}
$$

### Transformations Between Dimensions

Let's say there is a plane $\beta$ in $\mathbb{R}^3$ spanned by two vectors:
$$
\beta =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        1\\0\\1
    \end{bmatrix},
    \begin{bmatrix}
        1\\1\\0
    \end{bmatrix}
\end{Bmatrix}
$$
Now let's suppose there is a point on this plane:
$$
\vec{x} =
\begin{bmatrix}
    7\\-4
\end{bmatrix}
$$
What are the associated coordinates of $\vec{x}$ in our standard $\mathbb{R}^3$. Or that is, from the perspective of someone outside the plane $\beta$, how could you describe $\vec{x}$.

$$
\begin{bmatrix}
    1&0\\0&1
\end{bmatrix}
\begin{bmatrix}
    7\\-4
\end{bmatrix}
$$
Where in this case the $2\times2$ identity matrix represents the basis of our plane $\beta$.

Represent $\beta$ as the column space of a matrix $B$
$$
\begin{bmatrix}
    1&1\\
    0&1\\
    1&0
\end{bmatrix}
\begin{bmatrix}
    1&0\\0&1
\end{bmatrix}
\begin{bmatrix}
    7\\-4
\end{bmatrix}
=
\begin{bmatrix}
    3\\-4\\7
\end{bmatrix}
$$
So we simply multiply $B\vec{x}$:

Notice that as a transformation $B$ is injective, but not surjective. Every vector on our plane maps into a vector in $\mathbb{R}^3$, but not all vectors in $\mathbb{R}^3$ are in $\beta$.

Now suppose we were given a vector $\vec{y}$ in $\mathbb{R}^3$ and we were told that it is on our plane $\beta$. How could we determine the coordinates of $\vec{y}$ in $\beta$???

Let's say $\vec{y}$ is :
$$
\vec{y} =
\begin{bmatrix}
    10\\2\\8
\end{bmatrix}
$$

Well we would hopefully want to find some matrix $A$ that we could multiply to $B$ that would return the $2\times2$ identity matrix:
$$
AB = I_2
$$

In this case the basis of the vector space we're *sitting* in would be expressed as the standard basis for something in $\mathbb{R}^n$. Again, the basis for $\beta$ is **not** the *standard basis* $\{e_1,e_2\}$, but for the purposes of the vectors *living* in $\beta$ it might as well be!

So that's why we want to find some matrix $A$ that will change our perspective to be in $\beta$.

The best way to find $A$ is to simply form an augmented matrix: $\left[B|I_3\right]$ and row reduce until we've formed $I_3$:
$$
\begin{bmatrix}
    1&1&0&\big|&1&0&0\\
    0&1&0&\big|&0&1&0\\
    1&0&0&\big|&0&0&1\\
\end{bmatrix}
{\huge\rightarrow}
\begin{bmatrix}
    1&0&0&\big|&1&-1&0\\
    0&1&0&\big|&0&1&0\\
    0&0&1&\big|&-1&0&1
\end{bmatrix}
$$
This gives us the rectangular matrix:
$$
A =
\begin{bmatrix}
    1&-1&0\\
    0&1&0
\end{bmatrix}
$$
and in fact if we apply this to $B$ we get the $2\times2$ identity:
$$
AB =
\begin{bmatrix}
    1&-1&0\\
    0&1&0
\end{bmatrix}
\begin{bmatrix}
    1&1\\
    0&1\\
    1&0
\end{bmatrix}
=
\begin{bmatrix}
    1&0\\0&1
\end{bmatrix}
$$

***WARNING!!!*** This is not the same as saying $A=B^{-1}$, $B$ is **not** invertible. If $B$ was invertible and it's inverse was $A$ then $B$ would commute with $A$: $AB = BA = I$. This is not true so we cannot call $A$ $B$'s inverse, nor call $B$ invertible.

so applying $A$ to $\vec{y}$ we get:
$$
A\vec{y} =
\begin{bmatrix}
    1&-1&0\\
    0&1&0
\end{bmatrix}
\begin{bmatrix}
    10\\2\\8
\end{bmatrix}
=
\begin{bmatrix}
    8\\2
\end{bmatrix}
$$
Notice that $A$ is also not injective, that means that not every vector in $\mathbb{R}^3$ will map perfectly on to the plane $\beta$, which corresponds with $B$ not being surjective.

Let's say we have some random point $\vec{u}$ in $\mathbb{R}^3$ that we multiply to $A$:
$$
\begin{bmatrix}
    1&-1&0\\
    0&1&0 
\end{bmatrix}
\begin{bmatrix}
    3\\4\\9
\end{bmatrix}
=
\begin{bmatrix}
    -1\\4
\end{bmatrix}
$$

Now let's find the $\ker(A)$, this is pretty easy, it's literally any vector with a $z$ component but no $x$ and $y$:
$$
\ker(A)
=
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        0\\0\\0
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\0\\1
    \end{bmatrix}
\end{Bmatrix}
$$
If you notice this vector is **orthogonal** to the vectors in $\beta$!!

So when we apply $A$ to some arbitrary vector in $\mathbb{R}^3$ we actually **project** that vector on to $\beta$, or in other words $A\vec{x} = \text{proj}_\beta(\vec{x})$. And the $\ker(A)$ in this case means $\vec{y}\in\mathbb{R}^3$ where $A\vec{y}\not\in\beta$. Which is $\beta$'s **orthogonal complement** $\beta^\perp$.

This has a wider intuition that rectangular $m\times n$ matrices act as transformations *between* dimensions where if $m>n$ you are projecting from one hyperplane to a lower dimensional hyperplane, while if $m<n$ you are expressing elements of one hyperplane in higher dimensional terms.

*A hyperplane is simply an abstraction of a the 2D plane for higher dimensions, a 3D hyperplane might look something like a cube, while a 2D is a regular plane, and a 1D hyperplane is simply a line. Usually the dimension of the hyperplane is one lower than the actual dimension of the geometry, so a line would be a 0-plane and a the 2D plane a 1-plane, etc.*

### Vector Dot Product as Transformations

Working off of our intuition from earlier, we notice that we already know of a way to express a projection from one vector to another. The **dot product**!

In fact we could sincerely write the dot product as a linear transformation:
$$
\vec{u}\cdot\vec{v} =
u_1v_1+u_2v_2+...+u_nv_n
=
\begin{bmatrix}
    u_1&u_2&\cdots&u_n
\end{bmatrix}
\begin{bmatrix}
    v_1\\v_2\\\vdots\\v_n
\end{bmatrix}
=\vec{u}^T\vec{v}
$$

In essence, the dot product is a transformation from a Vector Space to it's associate Field $T:V(\mathbb{K})\rightarrow\mathbb{K}$. This is like we're moving down all of our  dimensions to a single number line.

Let's take an example for polynomials:
$$
\begin{bmatrix}
    3&-5&4
\end{bmatrix}
\begin{bmatrix}
    x^2\\x\\1
\end{bmatrix}
= 3x^2-5x+4
$$
This kind of makes sense when we think about $3x^2-5x+4$ being a linear combination of our basis $\{x^2,x,1\}$. The row matrix $[3\quad-5\quad4]$ simply represents that linear combination as a transformation.

### Determinants and Transformations

The determinant is the scaling coefficient of the volume between our vectors.

### Change of Basis

This requires a very similar intuition to the section on rectangular transformations. Except instead of **linear transformations** between hyperplanes we are actually looking at linear **operators**.

Rather than having $\beta$ be an embedded space in $\mathbb{R}^3$ we can think of $\beta$ as a subspace that spans $\mathbb{R}^3$:
$$
\beta =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        1\\0\\1
    \end{bmatrix}
    ,
    \begin{bmatrix}
        1\\1\\0
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\2\\1
    \end{bmatrix}
\end{Bmatrix}
$$

Now let's suppose we had another subspace that spanned $\mathbb{R}^3$ called $\alpha$:
$$
\alpha =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        2\\0\\1
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\-1\\2
    \end{bmatrix}
    ,
    \begin{bmatrix}
        2\\0\\3
    \end{bmatrix}
\end{Bmatrix}
$$

I will call the standard basis $\epsilon = \{e_1,e_2,e_3\}$, which is:
$$
\epsilon =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        1\\0\\0
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\1\\0
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\0\\1
    \end{bmatrix}
\end{Bmatrix}
$$

Notice that since $\alpha$ and $\beta$ form a basis for $\mathbb{R}^3$, we have 3 linearly independent vectors, this means we can reduce matrix forms of $\beta$ and $\alpha$ to the $3\times3$ identity. This has the intuition of taking $\alpha$ or $\beta$ as some arbitrary *standard* basis that we can express all of $\mathbb{R}^3$ in. Since these can be reduced to the identity we know they must represent isomorphisms. So they can be **inverted**!!

But what does it even mean to invert a basis?

You see the answer is in perspective: notice that if we were some vector, living in $\beta$, we wouldn't really think about the actual vectors themselves in terms of the standard basis. To us the basis of $\beta$ **is** the standard basis. I'm going to represent that as the relationship:
$$
\beta^{-1}\circ\beta=\epsilon
$$
where we can think of $\beta^{-1}$ as sort of removing the vectors to make them appear *standard*.

If we had a vector $x$ in our regular $\mathbb{R}^3$ and we wanted to know what someone in $\beta$ would observe that vector as: well we just need to think about how someone in $\beta$ would see that vector, and they would look at it like:
$$
\beta^{-1}(x) = [x]_\beta
$$

This translates the same with other basis. If we had a vector in $\alpha$ and wanted to see hows someone in $\beta$ would describe that vector we can basically take:
$$
\beta^{-1}\circ\alpha(x) = [x_\alpha]_\beta
$$

So let's find these inverse basis.
$$
\beta^{-1} =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        -1\\2\\-1
    \end{bmatrix}
    ,
    \begin{bmatrix}
        -1\\1\\0
    \end{bmatrix}
    ,
    \begin{bmatrix}
        2\\-2\\1
    \end{bmatrix}
\end{Bmatrix}
$$
Notice this is really just inverting the matrix $B$ where $\text{col}(B) = \beta$, and then taking $\text{col}\left(B^{-1}\right)$. We can do the same for $\alpha$.
$$
\alpha^{-1} =
\text{span}
\begin{Bmatrix}
    \begin{bmatrix}
        {3\over4}\\0\\-{1\over4}
    \end{bmatrix}
    ,
    \begin{bmatrix}
        0\\-1\\1
    \end{bmatrix}
    ,
    \begin{bmatrix}
        -{1\over2}\\0\\{1\over2}
    \end{bmatrix}
\end{Bmatrix}
$$

Now if we think about what it means to represent a vector in $\beta$ or $\alpha$ in terms of our standard basis $\epsilon$, well we can simply remember that in this case $\epsilon$ is an identity operator and involutory.

In the language of matrix multiplication we're essentially looking at something like:
$$
TAx = By
$$
where $A$ and $B$ are matrices representing $\alpha$ and $\beta$, and $T$ represents some general transformation. $x$ and $y$ represent linear combinations of $\alpha$ an $\beta$ vectors. The term $By$ and $Ax$ simply refer to making a vector in $\beta$ and $\alpha$ from the point $y$ and $x$.

Notice how if we invert $B$ we could write $y$ as:
$$
B^{-1}TAx = y
$$
and now we've managed to describe a complete transformation on $x$.
So if we had a vector $\vec{x}$ in our standard basis and wanted to see how someone in $\beta$ would see that vector we can think of applying $\epsilon^{-1}\beta(\vec{x})$ which is nothing more than $\beta(\vec{x})$:
$$
\begin{bmatrix}
    1&1&0\\
    0&1&2\\
    1&0&1
\end{bmatrix}
\begin{bmatrix}
    2\\3\\-1
\end{bmatrix}
=
\begin{bmatrix}
    5\\1\\1
\end{bmatrix}
$$
So the vector that represents $2e_1+3e_2-e_3\in\epsilon$ represents the vector $5b_1+b_2+b_3\in\beta$.

Likewise to transform from $\alpha$ to $\epsilon$ we we can do the same thing.

Now what if we had a vector $\vec{x}_\beta$ that we wanted to represent in our standard basis? Well we can just take:
$$
\beta^{-1}\circ\epsilon(\vec{x})
$$
Again, think of the intuition of *reversing* or eliminating a particular perspective.

Now what if we wanted to represent a vector in $\beta$ as a vector in $\alpha$ then the change of basis operator would be:
$$
\alpha^{-1}\circ\beta(\vec{x})
$$
which is represented through the matrix multiplication:
$$
\begin{bmatrix}
    {3\over4}&0&-{1\over2}\\
    0&-1&0\\
    -{1\over4}&1&{1\over2}
\end{bmatrix}
\begin{bmatrix}
    1&1&0\\
    0&1&2\\
    1&0&1
\end{bmatrix}
\begin{bmatrix}
    2\\3\\-1
\end{bmatrix}
$$
Which is the same operation as:
$$
\begin{bmatrix}
    {3\over4}&0&-{1\over2}\\
    0&-1&0\\
    -{1\over4}&1&{1\over2}
\end{bmatrix}
\begin{bmatrix}
    5\\1\\1
\end{bmatrix}
$$
Again think of the relationship:
$$
Ax = By
$$
$x$ and $y$ are just different ways to interpret the same vector, going from one basis to another is simply multiplying by the inverse of the basis we want to go to!
