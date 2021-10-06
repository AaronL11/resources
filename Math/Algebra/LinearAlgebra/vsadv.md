\newpage

# Advanced Vector Spaces

At this point we are going to be touching on a lot more advanced mathematics and I will be using and talking about advanced concepts from other parts of mathematics. If things become too difficult take the time to go back and look at the other videos and pages I've done, particularly in terms of set theory and abstract algebra.

## Special Vector Operations

### Inner Product

The inner product is a binary operation that takes two vectors and returns a scalar element. This naturally allows us to define a *norm* for each vector $||x||$.

If $V$ is a vector space over $\mathbb{F}$ then the inner product $\langle\cdot,\cdot\rangle$ is defined as:
$$
\langle\cdot,\cdot\rangle:V\times V \rightarrow \mathbb{F}
$$

The defining properties of the inner product are:

1. Linearity in the first argument
    $$
    \begin{aligned}
    \langle ax.y \rangle = a\langle x,y \rangle\\
    \langle x+y,z\rangle = \langle x,y \rangle + \langle z,y \rangle
    \end{aligned}
    $$
2. Conjugate Symmetry
    $$
    \langle x,y \rangle = \langle y,x \rangle^*
    $$
3. positive definiteness
    $$
    \langle x,y \rangle \ge 0
    $$

A vector space that has an inner product is called an **inner product space**. An example of an inner product space is $\mathbb{R}^n$. The *dot product* between two vectors is the inner product.

### Outer Product
$$
\vec{v}\otimes \vec{u} =\vec{v}\vec{u}^T
$$

$$
\begin{bmatrix}
    v_1\\v_2\\\vdots\\v_n
\end{bmatrix}
\begin{bmatrix}
    u_1&u_2&\cdots&u_n
\end{bmatrix}
=
\begin{bmatrix}
    v_1u_1&v_1u_2&\cdots&v_1u_n\\
    v_1u_1&v_2u_2&&\vdots\\
    \vdots&&\ddots\\
    v_nu_1&\cdots&&v_nu_n
\end{bmatrix}
$$

notice that $\text{tr}(v\otimes u) = \langle v,u\rangle$

A vector space endowed with an outer product operation is called an **outer product space**.

### Exterior (Wedge) Product

A vector space with a wedge product is called an **exterior product space**.

## Special Vector Spaces

### Normed Vector Space

### Banach Space

### Hilbert Space

A **Hilbert Space** is an inner product space 

Essentially a hilbert space is a normed banach space.

Any inner product space can be extended into a hilbert space

### Axioms

## Outer Product


## Exterior Product

The exterior or **wedge** product is an abstraction of the cross product

## Banach Spaces
