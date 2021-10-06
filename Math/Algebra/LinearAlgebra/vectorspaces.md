\newpage

# Vector Spaces

## What is a Vector?

We shall begin by asking what a vector is.

For those who've got a bit of physics you might recognize a vector as a point in space, with a magnitude and momentum. for those who've done a bit of programming and linear algebra already you know that we can also represent these as row and column matrices.
$$
\begin{bmatrix}
   a&b&c
\end{bmatrix}
\qquad\qquad
\begin{bmatrix}
   a\\b\\c
\end{bmatrix}
$$

I'm going to change the definition of what a vector is by .

A vector is an element of a Vector Space that can be added

## Vector Properties

### Magnitude (Norm)

The magnitude of a vector is it's length

### Angle

### Unit Vectors

Unit vectors are vectors with a norm of 1.

We denote this with a little hat or circumflex, $\hat{v}$, over the vector to make it stand out.

We can create a unit vector from a vector by dividing the vector by it's norm:
$$
\hat{v} = {\vec{v}\over||\vec{v}||}
$$

This allows us to redefine a vector in terms of it's magnitude and direction:
$$
\vec{v} = ||\vec{v}||\hat{v}
$$

## What is a Vector Space?

### Axioms

### Examples

This ultimately makes us asks, can we form **linear combinations** and is there a zero vector included.

## Additional Vector Operations

For the current context I will only be discussing operations for vectors in $\mathbb{R}^n$. However there are other abstractions of these operations that will be discussed in the *advanced* section.

### Dot Product

The dot product is a multiplication operation between vectors, essentially it takes two vectors and returns a scalar by multiplying 
$$
\begin{pmatrix}
   a\\b\\c
\end{pmatrix}
\cdot
\begin{pmatrix}
   d\\e\\f
\end{pmatrix}
=
ad+be+cf
$$
For two arbitrary $n$-th dimensional vectors $\vec{v},\vec{u}\in\mathbb{R}^n$, their dot product is defined as:
$$
\vec{u}\cdot\vec{v} = \sum_{i=1}^nv_iu_i
$$

The dot product of a vector with itself basically gives us pythagoras's theorem, or the vector's length this allows us to define a norm over our vectors:
$$
\vec{v}\cdot\vec{v} = ||\vec{v}||^2
$$

### Cross Product

The cross product is special operation that is only really used in 2 dimensional and 3 dimensional vectors. Essentially the cross product is an operation between vectors that returns another vector.

In the case of two vectors $\vec{v},\vec{u}\in\mathbb{R}^2$, their crossproduct is a vector perpendicular to both of them:
$$
\vec{v}\times\vec{u} = \hat{n}
$$

$$
ad-cb
$$

For 3 dimensional vectors this changes:

### Distance between two vectors

The distance between two vectors is quite simply the length of the vector between them:
$$
d(\vec{v},\vec{w}) = ||\vec{v}-\vec{w}||
$$

### Vector Projection

$$
\text{proj}_{\vec{v}}(\vec{w}) = {\vec{v}\cdot\vec{w}\over||\vec{v}||^2}\vec{v}
$$

## Orthogonality

$$
\vec{v}\cdot\vec{u} = 0
$$

If the vectors also happen to be unit vectors, then we call this set *orthonormal*.

### Fourier Expansion

$$
\text{fourier}(\vec{x}) = \sum_i^n\text{proj}_{\vec{f}_i}(\vec{x})
$$

### Gram-Smidt Process

$$
\begin{aligned}
f_1 &= v_1\\
f_2 &= v_2 - \text{proj}_{f_1}(v_2)\\
f_3 &= v_3 - \left(\text{proj}_{f_2}(v_3) + \text{proj}_{f_1}(v_3)\right)\\
f_n &= v_n - \sum_i^{n-1}\text{proj}_{f_i}(v_n)
\end{aligned}
$$

## Homomorphisms

A homomorphism is a structure preserving map
$$
\begin{aligned}
   f:(G,+)&\rightarrow(H,\diamond)\\
   a&\mapsto f(a)
\end{aligned}
$$
where the operations are preserved
$$
f(a+b) = f(a)\diamond f(b)
$$

In the context of a vector space that operation is vector addition.

It is called an 

## Vectors as Linear Equations

### Spanning Sets

$$
av + bw = \text{span}\{v,w\}
$$

### Linear Independence

### Basis

A basis is a linearly independent set of vectors whose span forms a subspace.

### Subspaces


The dimension of a subspace is the number of linearly independent vectors in that subspace, or essentially the amount of basis vectors in $U$.
$$
\text{dim}(U)
$$


### Subspace Projection

$U = \{\vec{u}_1,\vec{u}_2,..,\vec{u}_n\}$

$$
\text{proj}_U(\vec{x}) = \sum_{i=1}^n\text{proj}_{\vec{u}_i}(\vec{x}),\quad\forall\vec{u}_i\in U
$$

## Examples of Vector Spaces and Subspaces

1. $\mathbb{R}^n$
   * The standard vector space we are used to working in
2. $M_{nn}(\mathbb{F})$
   * Vector Space of $n\times n$ matrices over some field
3. $P_n(\mathbb{F})$
   * The vector space of polynomials over some field

We can also describe the complex numbers as vectors whose associated field is the real numbers:
$$
\mathbb{C} = \text{span}_\mathbb{R}\{1,i\}
$$
This extends to quaternions as well except we have two different formulations, one with complex and one with the reals:
$$
\mathbb{H}=\text{span}_\mathbb{C}\{1,j\} = \text{span}_\mathbb{R}\{1,i,j,k\}
$$

## Linear Transformations Between Vector Spaces

Tying into homomorphisms from Abstract Algebra, linear transformation (often called linear maps), are simply homomorphisms from one vector space to another. A linear transformation is defined:
$$
\begin{aligned}
T:V&\rightarrow W\\
v&\mapsto T(v)
\end{aligned}
$$
and is called a **linear** simply because it satisfies the property of linearity:
$$
T(av + bw) = aT(v) + bT(w)
$$
Ther are other transformations we can define between vector spaces, however in the context of linear algebra linear transformations are fundamental.

A linear transformation is called a linear operator if it is also an endomorphism $T:V\rightarrow V$

### Linear Equations and Linear Transformations

A linear transformation on $V$ can be defined as a system of linear equations taking elements in $V$ that retrun an element in $W$.

For example, take the linear $T:\mathbb{R}^3\rightarrow\mathbb{R}^4$ that is defined by these equations:
$$
T
\begin{pmatrix}
   x\\y\\z
\end{pmatrix}
{\huge\mapsto}
\begin{aligned}
3x + 4y - 2z &= 5\\
-x -2y +3z &= 4\\
-2x + 4y -3z &= 3\\
x-y-z &= 5
\end{aligned}
$$

blah blah blah

This means we can define the action of $T$ on $V$ based on what it does to the basis of $V$.

In order to describe linear transformations it's important to recognize and define certain structures and patterns within them. The following is a look into the properties of linear transformations that are useful.

### Kernel and Image

Do you remember in the part about systems of equations where I mentioned solving a system of equations only to find that there were infinite solutions? If we recall our example, we ended up finding a vector where any linear combination of that vector would map to zero.

This happens to become an important part of that particular transformation, these vectors have the relationship $T(\vec{v}) = \vec{0}$. There may be multiple vectors, and it could be useful to understand what those vectors are.

This set of vectors is called the kernel of $T$, $\text{ker}(T)$, notice that this forms a subspace of the domain $V$ since those are the vectors the transformation is being applied to:
$$
\ker (T) = \{\vec{v}\in V:T(\vec{v})=\vec{0}\in W\}
$$
This becomes useful in allowing us to check injectivity, which we'll talk about soon.

Now what about the rest of the values in our domain? What about the codomain itself. Well if we look at the vectors that are completely mapped into our codomain. We could form a set of these vectors:
$$
\{T(v_1),T(v_2),..,T(v_n)\}
$$
This set is called the image of $T$, $\text{Im}(T)$, notice that this set is a subspace of the codomain $W$.
$$
\text{Im}(T) = \{\vec{w}\in W: T(\vec{v})=\vec{w},\quad\vec{v}\in V\}
$$
This is useful for finding surjectivity, which we'll talk about in the next chapter.

### Injectivity

A linear transformation is said to be injective if it maps every value in the domain to a uniqe value in the codomain. This is often mention as $T$ being *one-to-one*:
$$
\text{injective}(T) \iff T(\vec{v}_i) = T(\vec{v}_j) \rightarrow \vec{v}_i=\vec{v}_j,\quad\forall\vec{v}_i,\vec{v}_j\in V
$$
or
$$
\text{injective}(T) \iff T(\vec{v})\ne T(\vec{u}),\quad\forall(\vec{v},\vec{u})\in V\quad\vec{v}\ne\vec{u}
$$
and the negation is:
$$
\neg(\text{injective}(T)) \iff \exists(\vec{v},\vec{u})~\vec{v}\ne\vec{u}: T(\vec{v}) = T(\vec{u})
$$

Since the $\ker(T)$ tells us the set of vectors that map to zero, then if the kernel has values other than the standard zero vector, then we can find at least two vectors that map to the same value. Making our transformation non-injective.

This becomes a good way to look at vectors that map to the same value that isn't zero as well. Suppose there were two vectors that mapped to the same value in the codomain:
$$
T(v_1) = T(v_2) = w
$$
Well if we were to write $v_1$ and $v_2$ as sums of one vector $u$ with some arbitrary vectors $x_1,x_2\in\ker(T)$ then:
$$
\begin{aligned}
   T(v_1) = T(u+x_1) = T(u)+\vec{0}\\
   T(v_1) = T(u+x_2) = T(u)+\vec{0}
\end{aligned}
$$
So the kernel is enough to tell us whether or not $T$ is injective.

### Surjectivity

A linear transformation is **surjective** if it maps every vector in the domain to the entirety of the codomain. it is often said that $T$ is onto.

$$
\text{surjective}(T) \iff W = \{T(\vec{v}):\vec{v}\in V\}
$$
or
$$
\text{surjective}(T) \iff W = \text{Im}(T)
$$
and it's negation would be:
$$
\neg(\text{surjective}(T)) \iff \exists\vec{w}\in W:\text{Im}(T)\not\ni\vec{w}
$$
So if we can find a vector in our codomain that is not an element of $T$'s image, we have shown that $T$ is not surjective.

### Isomorphic Maps and Inverse Transformations

A linear transformation is an **isomorphism** if it is **bijective** (injective & surjective). Since an isomorphic map maps all values in our domain to a unique value in our codomain and no two values in the domain map to each other, then we could almost imagine a reverse mapping that maps every elment in our codomain to the original element in the domain.

This would be the **inverse** of our transformation and all isomorphic maps are invertible, that is:
$$
\exists(T^{-1}:W\rightarrow V) : T^{-1}\circ T(x) = x, \forall x\in V~~\forall T(x)\in W
$$
We can find the inverse the same way we found the inverse in the linear system of equations section. However we will soon find a nicer way to represent linear transformations.

Time to move on to **MATRICES**!!
