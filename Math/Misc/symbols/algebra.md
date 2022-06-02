\newpage

# Algebra

## Prime Numbers ($\mathbb{P}$)

The prime numbers are numbers which can not be factored into the product of other numbers. The prime numbers don't include one as one can be factored into itself multiple times, it can also be factored into every other prime.
$$
\mathbb{P} = \{2,3,5,7,11,13...\infty\}
$$

## Natural Numbers ($\mathbb{N}$)

The natural numbers is the set of counting numbers. These are the numbers we learn in grade school when we first learn basic arithmetic and counting. 1 apple, 2 apples, 3 apples, etc.
$$
\mathbb{N} = \{0,1,2..,\infty\}
$$

The natural numbers come in two flavours, one with zero $\mathbb{N}_0$ and one without zero $\mathbb{N}_1$. The reason for ommiting zero is a philosophical debate that is beyond the scope of this presentation, so we won't be talking about it.

The natural numbers are closed under addition and multiplication. That is to say that if we have two natural numbers and we add or multiply them together, the result is another natural number:
$$
\begin{aligned}
    a+b\in\mathbb{N},&\quad\forall a,b\in\mathbb{N}\\
    ab\in\mathbb{N},&\quad\forall a,b\in\mathbb{N}
\end{aligned}
$$

## Integer Numbers ($\mathbb{Z}$)

The integers are natural numbers but we include negative values:
$$
\mathbb{Z} = \{-\infty,..,-1,0,1,..,\infty\}
$$
The Z stands for the german word *Zahlen*, which means an integer number.

One of the key algebraic properties between the natural numbers and the integers is that the integers are closed under addition and it's inverse operation subtraction. If you notice, the sum of two natural numbers is always a natural number, $2+2=4$, but that isn't the case with subtraction. Take $1-2$ for instance. In the integers you can always add or subtract two integers and get an integer back. The integers are also closed under multiplication:
$$
\begin{aligned}
    a\pm b\in\mathbb{Z},&\quad\forall a,b\in\mathbb{Z}\\
    ab\in\mathbb{Z},&\quad\forall a,b\in\mathbb{Z}
\end{aligned} 
$$

An important variant, the integers modulo $n$, is written like $\mathbb{Z}_n$ and is the set:
$$
\mathbb{Z}_n = \{0,1,2,..,n-1\}
$$
This is the set of all integers$\mod n$

## Rational Numbers ($\mathbb{Q}$)

The rational numbers is the set of all integer ratios:
$$
\mathbb{Q} = \{-\infty,..,-\tfrac{2}{1},-\tfrac{3}{2},-\tfrac{1}{1},0,\tfrac{1}{1},\tfrac{3}{2},\tfrac{2}{1},..,\infty\}
$$

## Algebraic Numbers ($\mathbb{A}$)

The algebraic numbers are all the numbers that are solutions to algebraic systems, mainly polynomial equations:
$$
\mathbb{A} = \{x~|~\sum_{i=0}^na_ix^i,\quad\forall a\in\mathbb{R}\}
$$

## Real Numbers ($\mathbb{R}$)

This is the most common set of numbers that you will encounter. Essentially the real numbers, often called the **reals**, is the set of rational and irrational numbers. Any number you can think of is contained inside the real numbers.
$$
\mathbb{R} = \{-\infty,..,-e,-{3\over2},0,1,\pi,..,\infty\}
$$

A corrollary to the real numbers is the irrational numbers: The irrational numbers is the set difference of the real numbers and the rational numbers $\mathbb{R}-\mathbb{Q}$:
$$
\mathbb{R}-\mathbb{Q} = \{-\infty,..,-\pi,-e,-\Phi,-\phi,0,\phi,\Phi,e,\pi,...,\infty\}
$$


## Imaginary Numbers ($\mathbb{I}$)

The imaginary numbers are simply every real number multiplied by the imaginary number $i=\sqrt{-1}$

$$
\mathbb{I} = \{-\infty i, ..,-2i,-i,0,i,2i,..,\infty i\}
$$

## Complex Numbers ($\mathbb{C}$)

The complex numbers are essentially linear combinations of the real and imaginary numbers:
$$
\mathbb{C} = \{a+bi : a,b\in\mathbb{R}\}
$$
This contains all real numbers and all imaginary numbers and forms the largest number set.
$$
\mathbb{C} = \{...,34(\cos{\pi\over72}+i\sin{\pi\over72}),-(5+6i),-i,-1,0,1,i,e^{i{\pi\over3}},3+5i,...\infty\}
$$

Complex numbers prove useful when forming an algebraic framework for dealing with 2 dimensional rotations. In the complex plane, multiplication by $i$ translates essentially to a rotation by 180 degrees:
$$
i(1+i) = e^{i{\pi\over2}}e^{i{\pi\over4}} = -1+i = e^{-\pi\over4}
$$

## Quaternions ($\mathbb{H}$)

Quaternions are similar to the complex numbers except they have a few more imaginary values $j$ and $k$ which are related to $1$ and $i$ through the following identities:
$$
\begin{aligned}
    ij &= k  &\quad jk &= i  &\quad ki &= j\\
    ji &= -k &\quad kj &= -i &\quad ik &= -j\\
    ij &= -ji&\quad kj &= -jk&\quad ki &= -ik
\end{aligned}\\
-1 = i^2 = j^2 = k^2
$$

Quaternions are essentially linear combinations of $1,i,j,k$:

It can also be written as the linear combination of $c+dj$:
$$
\mathbb{H} = \{c+dj:c,d\in\mathbb{C}\} = \{a+bi+cj+dk:a,b,c,d\in\mathbb{R}\}
$$
It's important to note that the quaternions **do not** form an associative algebra over the complex numbers, they are a vector space over the real numbers.

Quaternions are useful because they allow us to describe rotations in 3D space. This can easily be seen when we describe the quaternions as being $c+dj$ with a complex $c$ and $d$. Both $c$ and $d$ describe changes in one angel, and since we have two angles we are now able to describe rotations in 3D space.

Take the quaternion $1+i+j+k$, this can be factored into $c,d=(1+i)$, $(1+i)+(1+i)j$.

If we multiply the left side by $i$ we will get:
$$
i(1+i+j+k) = i+i^2 + ij + ik = -1 + i -j +k
$$
Our result is equivalent to $(-1+i) + (-1+i)j$. Which is equivalent to rotating the real components of $c$ and $d$ by $-\pi$.

If we were to multiply by $i$ on the right we will get:
$$
(1+i+j+k)i = i+i^2 +ji+ki = -1 + i + j - k
$$
Our result is equivalent to $(-1+i) + (1-i)j$ which is equivalent to rotating the real part of $c$ and the imaginary part of $d$ by $-\pi$

## Octonions ($\mathbb{O}$)

Octonions are 

## Boolean Domain ($\mathbb{B}$)

The boolean domain is the the domain of True and False. Written usually as 1s and 0s respectively. It's mainly used in computer science.
$$
\mathbb{B} = \{0,1\}
$$

## maps to ($\mapsto$)

## proportional to ($\propto$)