\newpage

# Basic Spectral Theory

## Eigenvectors and Eigenvalues

One thing that we might be curious about are vectors that appear unchanged under a linear transformation:
$$
Ax = x
$$
where $A\in M_{mn}$.

An example of a vector like this is the zero vector of the codomain of $A$, $\vec{0}_n$. However when we think about it, this transformation is essentially taking a vector and then scaling it by one, so a more general form of this relationship is a vector that, under a linear transformation, maps to itself times a scalar constant $\lambda$.
$$
Ax=\lambda x
$$
again $\vec{0}_n$ always satisfies this equation. Additionally, you may notice that if $x\in\text{ker}(A)$ then:
$$
Ax = 0x = \vec{0}_m
$$
where $\vec{0}_m$ is the zero vector in the codomain of $A$.

The vector $x$ that satisfies this equation is called an **eigenvector**, and the scalar $\lambda$ is it's **eigenvalue**, *eigen* being the german word for characteristic. As we have already shown 0 and $\vec{0}_n$ are already trivial eigenvalues and eigenvectors of $A$. But how can we go about finding other eigenvectors and eigenvalues of $A$?

One way to think about this is by rearranging the equation:
$$
Ax - \lambda x = \vec{0}_m
$$
and using linearity of matrix multiplication and the fact that $\lambda x = \lambda Ix$ then:
$$
(A-\lambda I)x = \vec{0}_m
$$
this means that $x\in\text{ker}(A-\lambda I)\quad\forall\lambda$. So we've found a way to find $x$ in terms of $\lambda$. However we still don't know how to find $\lambda$. Well since $\text{ker}(A-\lambda I)$ has a vector other than $\vec{0}_n$ then that means it's non-injective, and as a result not an isomorphism. This mean that the determinant must be zero, so we can set the equation:
$$
\det|A-\lambda I| = 0
$$
Since the terms along the diagonal of our matrix will look like: $(a-\lambda)$ the determinant will give us a polynomial in terms $\lambda$ called the characteristic polynomial, or eigenpolynomial. We can solve that polynomial to find our eigenvalues, then for each eigenvalue $\lambda$ solve for $\text{ker}(A-\lambda I)$ to get our eigenvectors.

Notice we could have done this the other way and done $\lambda I-A$, we would have found the same eigenvalues and eigenvectors.

### Diagonal Matrices

$$
\begin{vmatrix}
    a-\lambda&0&0\\
    0&b-\lambda&0\\
    0&0&c-\lambda\\
\end{vmatrix}
=
(a-\lambda)(b-\lambda)(c-\lambda) = 0
$$
The eigenvalues of a diagonal matrix are simply it's diagonal entries. The same holds true for triangular matrix, hessenberg, and tridiagonal matrices as their determinants are all products of the diagonal entries.

### Example

### Shortcuts for $2\times2$

$$
\begin{aligned}
\begin{vmatrix}
    a-\lambda&b\\
    c&d-\lambda
\end{vmatrix}
&=
(a-\lambda)(d-\lambda) - bc\\
&= \lambda^2 -(a+d)\lambda + (ad-dc)
\end{aligned}
$$
which could be simplified in terms of $A$'s trace and determinant:
$$
\lambda^2 - \text{tr}(A)\lambda + \det(A)
$$
and applying the quadratic formula:
$$
\lambda = {\text{tr}(A) \pm \sqrt{\text{tr}^2(A) - 4\det(A)}\over2}
$$

### Numerical Methods

One thing to note is that solving higher degree polynomials is not always practical, in fact it can be rather tedious and so there are other iterative methods to finding eigenvalue that are more efficient. However we will discuss those more in depth when we talk about numerical linear algebra.

## Diagonalization

### Diagonalizing a Matrix

$$
A = P^{-1}DP
$$

### Orthogonally Diagonalizing a Matrix


## Jordan Canonical (Normal) Form

$$
A = P^{-1}JP
$$

<!-- $$
J=
\begin{bmatrix}
    
\end{bmatrix}
$$ -->

## Singular Value Decomposition

One big question that should be popping into your head about diagonalization is: **what about rectangular matrices**??

$$
X = U\Sigma V^T
$$

$$
X = \hat{U}\hat{\Sigma}V^T
$$
This is known as the *economy SVD*.