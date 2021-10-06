\newpage

# Advanced Matrices

## Quadratic Forms

$$
P(x) = y^TAx
$$

Take a the curve:
$$
(x+1)x^2 + x^2y + x
$$
This can be represented via the dot product:
$$
\left(
\begin{bmatrix}
    x+1\\x^2\\x
\end{bmatrix}
\right)^T
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
$$
Which can be written as the following transformation:
$$
\left(
\begin{bmatrix}
    0&1&1\\
    1&0&0\\
    0&1&0
\end{bmatrix}
\begin{bmatrix}
    x^2\\x\\1
\end{bmatrix}
\right)^T
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
$$
Applying the transpose we get:
$$
\begin{bmatrix}
    x^2&x&1
\end{bmatrix}
\begin{bmatrix}
    0&1&0\\
    1&0&1\\
    1&0&0
\end{bmatrix}
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
$$
Now this is excluding any coefficients, for general coefficientes $a,b,c$ we have:
$$
\begin{bmatrix}
    x^2&x&1
\end{bmatrix}
\begin{bmatrix}
    0&1&0\\
    1&0&1\\
    1&0&0
\end{bmatrix}
\begin{bmatrix}
    a&0&0\\
    0&b&0\\
    0&0&c
\end{bmatrix}
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
$$
which can be simplified as:
$$
\begin{bmatrix}
    x^2&x&1
\end{bmatrix}
\begin{bmatrix}
    0&b&0\\
    a&0&c\\
    a&0&0
\end{bmatrix}
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
$$

So for a general we have:
$$
P(x,y) = 
$$

### Example in 3 variables:

$$
(x+1)y^2+zx^2y+z^2
$$

$$
\left(
\begin{bmatrix}
    1\\x^2y\\(x+1)y^2
\end{bmatrix}
\right)^T
\begin{bmatrix}
    z^2\\z\\1
\end{bmatrix}
$$

The left vector we can already see as being our prev
$$
\left(
\begin{bmatrix}
    0&0&1\\
    0&1&0\\
    1&0&0
\end{bmatrix}
\begin{bmatrix}
    (x+1)y^2\\x^2y\\1
\end{bmatrix}
\right)^T
\begin{bmatrix}
    z^2\\z\\1
\end{bmatrix}
$$

$$
\left(
\begin{bmatrix}
    0&0&1\\
    0&1&0\\
    1&0&0
\end{bmatrix}
\begin{bmatrix}
    x^2&x&1
\end{bmatrix}
\begin{bmatrix}
    0&1&0\\
    1&0&0\\
    1&0&1
\end{bmatrix}
\begin{bmatrix}
    y^2\\y\\1
\end{bmatrix}
\right)^T
\begin{bmatrix}
    z^2\\z\\1
\end{bmatrix}
$$

$$
\begin{bmatrix}
    y^2&y&1
\end{bmatrix}
\begin{bmatrix}
    0&1&1\\
    1&0&0\\
    0&0&1
\end{bmatrix}
\begin{bmatrix}
    x^2\\x\\1
\end{bmatrix}
\begin{bmatrix}
    0&0&1\\
    0&1&0\\
    1&0&0
\end{bmatrix}
\begin{bmatrix}
    z^2\\z\\1
\end{bmatrix}
$$


In general, a polynomial in $n$ variables is given recursively by:
$$
P(x_1,x_2,..,x_n) = P^T(\vec{x}_1,\vec{x}_2,..,\vec{x}_{n-1})\beta C\vec{x}_n
$$
Where $\beta$ is our basis and $C$ is the coefficients for the vector representing powers of the $n$-th variable.

## Matrix Applications

### Markov Matrices

### Linear Dynamical Systems (LDS)

## Matrix Decompositions

These are some useful and powerful optimizations and algorithms for matrices. As well as other applications

### LU Decomposition

The $LU$ decomposition is useful for calculating things like determinants for general $n\times n$ matrices. We know that the determinant for a triangular matrix is simply the product of the diagonal entries, and the determinant of the product of two matrices is the product of their determinants:

So essentially if we can decompose a matrix $A$ into:
$$
A = LU
$$
Where $U$ is *upper* triangule and $L$ is *lower* triangular, then $\det A$ is simply:
$$
\det A = \det L \cdot \det U
$$

Turning $A$ into an upper triangular matrix is pretty easy, simply put $A$ into REF, but how can we detrmine $L$?

This turns out to be even more simple. Remember how we can represent row reductions as transformations on $A$ via multiplication by elementary matrices?
$$
EA = U
$$
Well as it turns out, *if you used pivots to find REF*, then that matrix $E$ is lower triangular. This makes sense when you realize that all we're really doing is taking the pivot and multiplying downwards by the lowest common factor with the next row.
$$
\begin{aligned}
    &a_1x + b_1y + ...\\
    &a_2x + b_2y + ...\\
    &a_3x + b_3y + ...\\
    &\vdots
\end{aligned}
\quad{\huge\rightarrow}\quad
\begin{aligned}
    &a_1x + b_1y + ...\\
    &a_2x-\left(\tfrac{a_2}{a_1}a_1x\right) + b_2y-\left(\tfrac{a_2}{a_1}b_1y\right) + ... -{a_2\over a_1}(...\\
    &a_3x-\left(\tfrac{a_3}{a_1}a_1x\right) + b_3y-\left(\tfrac{a_3}{a_1}b_1y\right) + ... -a_3(...\\
    &\vdots
\end{aligned}
$$
If we were to continue this and apply that transformation to the identity matrix it would simply look like:
$$
\begin{bmatrix}
    1&0&0&\cdots&0\\
    0&1&0&\cdots&0\\
    0&0&1&\cdots&0\\
    \vdots&&&\ddots&\\
    0&0&0&\cdots&1
\end{bmatrix}
\quad{\huge\rightarrow}\quad
\begin{bmatrix}
    1&0&0&\cdots&0\\
    -{a_2\over a_1}&1&0&\cdots&0\\
    -{a_3\over a_1}&0&1&\cdots&0\\
    \vdots&&&\ddots&\vdots\\
    -{a_n\over a_1}&0&0&\cdots&1
\end{bmatrix}
\\
$$
And we can basically repeat that for all the other pivots.

**REMEMBER THAT THIS ONLY MAKES SENSE IF WE *DO NOT* SWAP ANY ROWS WHILE PUTTING OUR MATRIX INTO REF**

Now for the next bit we need to think about
$$
\begin{bmatrix}
    1&0&0&\cdots&0\\
    a&1&0&\cdots&0\\
    b&c&1&\cdots&0\\
    \vdots&&&\ddots&\vdots\\
    d&e&f&\cdots&1
\end{bmatrix}
$$
Well if we wanted to invert this matrix (i.e turn it into the identity), then we actually have a very simple algorithm. We can use pivots again and basically just subtract each coefficient, clean out the whole column, then repeat that on the next pivot.

So our inverse literally looks like the negative of anything below our diagonal:
$$
\begin{bmatrix}
    1&0&0&\cdots&0\\
    -a&1&0&\cdots&0\\
    -b&-c&1&\cdots&0\\
    \vdots&&&\ddots&\vdots\\
    -d&-e&-f&\cdots&1
\end{bmatrix}
$$

So as we go about applying $E$ to $A$, we can already get a look at it's inverse:
$$
E^{-1}=
\begin{bmatrix}
    1&0&0&\cdots&0\\
    {a_2\over a_1}&1&0&\cdots&0\\
    {a_3\over a_1}&\left(b_3-{a_3\over a_1}b_1\over b_2-{a_2\over a_1}b_1\right)&1&\cdots&0\\
    \vdots&&&\ddots&\vdots\\
    {a_n\over a_1}&\left(b_n-{a_n\over a_1}b_1\over b_2-{a_2\over a_1}b_1\right)&\left(c_n-{a_n\over a_1}b_1-{b_n-{a_n\over a_1}b_1\over b_2-{a_2\over a_1}b_1}\over c_3-{a_3\over a_1}b_1 -{b_3-{a_3\over a_1}b_1\over b_2-{a_2\over a_1}b_1t} \right)&\cdots&1
\end{bmatrix}
$$
Which while ugly will honestly make more sense as we go about applying our transformations.

So to wrap up, we put $A$ into REF, $U$, through a series of transformations $E$, and encode the inverse transformations $E^{-1}$, which is lower triangular $L$.
$$
\begin{aligned}
    EA &= U\\
    E^{-1}EA &= E^{-1}U,\quad L=E^{-1}\\
    \therefore A &= LU
\end{aligned}
$$
We also found a shortcut method to find $L$.

So let's try to decompose the following matrix:
$$
A=
\begin{bmatrix}
    1&1&0\\
    3&5&2\\
    1&3&12
\end{bmatrix}
$$
Let's row reduce into REF to find $U$:
$$
\begin{aligned} 
    &\begin{bmatrix}
        1&1&0\\
        3&5&2\\
        1&3&12
    \end{bmatrix}
    \begin{aligned}
        \underrightarrow{R_2-(3)R_1}
    \end{aligned}
    \begin{bmatrix}
        1&1&0\\
        0&2&2\\
        1&3&12
    \end{bmatrix}
    \begin{aligned}
        \underrightarrow{R_3-(1)R_1}
    \end{aligned}
    \begin{bmatrix}
        1&1&0\\
        0&2&2\\
        0&2&12
    \end{bmatrix}
\\
    &\begin{bmatrix}
        1&1&0\\
        0&2&2\\
        0&2&12
    \end{bmatrix}
    \begin{aligned}
        \underrightarrow{R_3-(1)R_2}
    \end{aligned}
    \begin{bmatrix}
        1&1&0\\
        0&2&2\\
        0&0&10
    \end{bmatrix}
    =U
\end{aligned}
$$
And all we do is write the coefficients of each row we're subtracting in the appropriate places
$$
L =
\begin{bmatrix}
    1&0&0\\
    3&1&0\\
    1&1&1
\end{bmatrix}
$$

And we've fully factored our matrix:
$$
\begin{aligned}
A&=LU\\
\begin{bmatrix}
    1&1&0\\
    3&5&2\\
    1&3&12
\end{bmatrix}
&=
\begin{bmatrix}
    1&0&0\\
    3&1&0\\
    1&1&1
\end{bmatrix}
\begin{bmatrix}
    1&1&0\\
    0&2&2\\
    0&0&10
\end{bmatrix}
\end{aligned}
$$
Now we can tell that it's determinant is 20, just multiply the diagonals!!

This is obviously more efficient for larger matrices, and is how most computers will calculate a matrix's determinant.

### Linear Least Squares

$$
(ax_1+b - y_1)^2 + (ax_2+b - y_2)^2 + ... + (ax_n+b-y_n)^2
$$

$$
\sum_i^n((ax_i+b)-y_i)^2
$$
$b=0$
$$
\sum_i^n(ax_i-y_i)^2
$$

This might look familiar, it is essentially the lenth of this vector:
$$
||A\vec{x}-\vec{y}||^2
$$

$$
||\vec{b}-A\vec{x}||^2 = 
$$

$$
A^TA\vec{x}^* = A^T\vec{b}
$$

### QR Decomposition

The QR Decomposition is an optimization strategy for solbing linear least squares problems. Essentially how it works is we want to decompose an $m\times n$ matrix $A$ into the product of an $m\times n$ matrix $Q$ and an $n\times n$ upper triangular matrix $R$.
$$
A = QR
$$
Now it's important that the $\text{col}(Q)$ forms an orthogonal basis. This means that the product:
$$
Q^TQ = I_n
$$


To find $Q$ we will apply Gram-Schmidt to the $\text{col}(A)$. We then normalize the vectors and this will form $\text{col}(Q)$

Finding $R$ becomes pretty easy as:
$$
Q^TA = Q^TQR = I_nR
$$
but why is $R$ upper triangular?

thus $R$ will be upper triangular.

So to tie this all back to least squares, remember that we want to find:
$$
A^TA\vec{x}^* = A^T\vec{b}
$$
When we apply the substitution $A=QR$ we can reduce this equation to:
$$
\begin{aligned}
    (QR)^TQR\vec{x}^* = (QR)^T\vec{b}\\
    R^TR\vec{x}^* = R^TQ^T\vec{b}\\
    \vec{x}^* = R^{-1}Q^T\vec{b}
\end{aligned}
$$
It will sometimes be the case where $R$ will not be invertible, and in that case there is **no** least squares solution. So we can also check if there are least squares solutions by checking if $\det R\ne0$.

So here's the process:

1. Apply Gram-Schmidt to $\text{col}(A)$ to find $\text{col}(Q)$
2. find $R = Q^TA$
3. check if $\det R \ne 0$, if zero we have no solutions
4. apply $R^{-1}Q^T\vec{b}$ to find $\vec{x}^*$

## Applying non Linear Functions to a Matrix

$$
\begin{aligned}
    e^A\\
    \cos A\\
    \sin A
\end{aligned}
$$

$$
e^A = A + {A^2\over2!} + {A^3\over3!} + ... + {A^k\over k!} + ... + {A^n\over n!}
$$


## Additional Matrix Operations

### Direct Sum

The direct sum of two matrices is a diagonal *block* matrix
$$
A\oplus B =
\begin{bmatrix}
    A&0\\0&B
\end{bmatrix}
$$

Multiple direct sums can be condensed with a large circle plus:
$$
\bigoplus_{i=1}^nA_i
$$

### Kronecker Product and Sum

The kronecker product is an operation between matrices:
$$
\begin{aligned}
    \otimes : M_{pm}(\mathbb{F})\times M_{qq}(\mathbb{F}) &\rightarrow M_{(p\times q)(m\times n)}(\mathbb{F})\\
    A\otimes B&\mapsto A_{ij}B
\end{aligned}
$$
Essentially we make a new matrix where each element is the right matrix scaled by each element in the left matrix.

For example:
$$
\begin{bmatrix}
    1&2\\3&4
\end{bmatrix}
\otimes
\begin{bmatrix}
    4&3\\2&1
\end{bmatrix}
=
\begin{bmatrix}
    1
    \begin{bmatrix}
        4&3\\2&1
    \end{bmatrix}
    &
    2
    \begin{bmatrix}
        4&3\\2&1
    \end{bmatrix}
    \\
    3
    \begin{bmatrix}
        4&3\\2&1
    \end{bmatrix}
    &
    4
    \begin{bmatrix}
        4&3\\2&1
    \end{bmatrix}
    \\
\end{bmatrix}
=
\begin{bmatrix}
    4&3&8&6\\
    2&1&4&2\\
    12&9&16&12\\
    6&3&8&4
\end{bmatrix}
$$

One interesting note is that:
$$
\begin{bmatrix}
    1&0&\cdots&0\\
    0&1&&\vdots\\
    \vdots&&\ddots\\
    0&\cdots&&1
\end{bmatrix}
\otimes
\begin{bmatrix}
    a_{11}&a_{12}&\cdots&a_{1n}\\
    a_{21}&a_{22}&&\vdots\\
    \vdots&&\ddots\\
    a_{m1}&\cdots&&a_{mn}
\end{bmatrix}
=
\begin{bmatrix}
    1A&0&\cdots&0\\
    0&1A&&\vdots\\
    \vdots&&\ddots\\
    0&\cdots&&1A
\end{bmatrix}
$$

If $A$ is an $m\times n$ matrix, then we have the following identity:
$$
I_m\otimes A = \bigoplus_1^m A
$$
where $\oplus$ is the direct sum.

The **Kronecker Sum** is defined as:
$$
A\oplus B = A\otimes I_m + I_n\otimes B
$$

$$

$$

For example:
$$
\begin{aligned}
    A &=
    \begin{bmatrix}
        1&2\\3&4
    \end{bmatrix}\\
    B &=
    \begin{bmatrix}
        5&6\\7&8
    \end{bmatrix}
\end{aligned}
$$
Their kronecker sum is :
$$
\begin{bmatrix}
    1&0&2&0\\
    0&1&0&2\\
    3&0&4&0\\
    0&3&0&4
\end{bmatrix}
+
\begin{bmatrix}
    5&6&0&0\\
    7&8&0&0\\
    0&0&5&6\\
    0&0&7&8
\end{bmatrix}
=
\begin{bmatrix}
    6&8&2&0\\
    7&9&0&2\\
    3&0&9&6\\
    0&3&7&12
\end{bmatrix}
$$

## Advanced Transformations

### Householder Transformations

Let me pose a simple problem that we've already breifly discussed way back at the start of this booklet. Say we wanted to rotate a vector about some axis

Complex conjugation can already do this rotation above the real line.

However, how can we reflect any arbitrary vector? and how can we express this as a matrix transformation $Px$?

We get the vector
$$
x + 2w
$$
where $w = -\langle x,v \rangle v$
$$
x - 2v(x^\dagger v)
$$
We can write $Px$ as the following matrix transformation:
$$
\left(I- 2vv^\dagger\right)x
$$
Which can be expressed in terms of an outer product on $v$:
$$
(I-2v\otimes v)x
$$

### Givens Rotations

One advantage givens rotations habe over householder transformations is that they can be easily parallelized. Additionally they are more efficient on sparse matrices.

### Other Derivative Stuff that is incomplete

Say we want to take the derivative of $ax^2+bx+c$, we know this to be $2ax+b$ from calculus class
$$
\begin{bmatrix}
    2&0&0\\
    0&1&0\\
    0&0&0
\end{bmatrix}
\begin{bmatrix}
    a\\b\\c
\end{bmatrix}
$$
We can also see that for 3 dimensions we have $D(ax^3+bx^2+cx+d) = 3a^2+2bx+c$ given by this transformation:
$$
\begin{bmatrix}
    3&0&0&0\\
    0&2&0&0\\
    0&0&1&0\\
    0&0&0&0
\end{bmatrix}
\begin{bmatrix}
    a\\b\\c\\d
\end{bmatrix}
$$
Which has the following construction
$$
[3]\oplus[2]\oplus[1]\oplus[0]
$$

$$
\left(
\bigoplus_i^n\begin{bmatrix}i\end{bmatrix}
\right)
\begin{bmatrix}
    a_0\\a_1\\\vdots\\a_n
\end{bmatrix}
$$

$$
\left(
\bigoplus_{i=2}^n\begin{bmatrix}i\end{bmatrix}\oplus\begin{bmatrix}1&0\end{bmatrix}
\right)
\begin{bmatrix}
    a_0\\a_1\\\vdots\\a_n
\end{bmatrix}
$$

If we were to apply the second derivative we would essentially be applying:
$$
\left(
\bigoplus_{i=2}^{n-2}\begin{bmatrix}i\end{bmatrix}\oplus\begin{bmatrix}1&0\end{bmatrix}
\right)
\left(
\bigoplus_{i=2}^n\begin{bmatrix}i\end{bmatrix}\oplus\begin{bmatrix}1&0\end{bmatrix}
\right)
\begin{bmatrix}
    a_0\\a_1\\\vdots\\a_n
\end{bmatrix}
$$

$D^kP_n(x)$

$$
\prod_i^k\left(\bigoplus_j^{n-(i+1)}\begin{bmatrix}j\end{bmatrix}\right)
\begin{bmatrix}
    a_0\\a_1\\\vdots\\a_n
\end{bmatrix}
$$
