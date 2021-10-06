
# Introduction

Hello everyone, today I'll be sharing something pretty close to my heart. This is a division algorithm for polynomials and the reason why I think it's special is because this is one of the few things in mathematics that I've actually discovered on my own. It's not very complicated, and I don't think it has many applications, but I hope you find it interesting nonetheless.

Before I go deeper into how the algorithm works, I want to take the time and build it from scratch with you. The only prerequisites for this will be a good understanding of linear algebra concepts such as linear transformations and dot products. We won't be using anything more advanced for now.

So let's think for a moment, you're in an undergraduate calculus class, and your exam just asked you to divide two polynomials. However you can't rememeber long division or synthetic division from your high school classes, so you're going to have to improvise. Let's see if we can use the rules of linear equations to find a way to divide these polynomials.

*yes this is actually the situation I found myself in when I came up with this, although at the time I was already familiar with linear algebra and vector spaces from previous self-study online. So don't feel too bad if some of this is new to you, we'll go through it together.*

## Polynomial Division

We'll start with finding a way to express dividing two polynomials.

You're probably all familiar with this formula
$$
{P(x)\over D(x)} = Q(x) + {R(x)\over D(x)}
$$
We can multiply by $D(x)$ to form this equivalent equation.
$$
P(x) = D(x)Q(x) + R(x)
$$

Now if we take the time and think about our product $D(x)Q(x)$, we might notice that this product must have the same degree as the degree of $P(x)$:
$$
\deg D(x)Q(x) = \deg P(x)
$$
Since multiplying two polynomials and taking their degree is the same as adding their degrees we can separate this out like so:
$$
\deg D(x) + \deg Q(x) = \deg P(x)
$$
This means the degree of $Q(x)$ is equal to the degree of $P(x)$ minus the degree of $D(x)$:
$$
\deg Q(x) = \deg P(x) - \deg D(x)
$$

Finding the degree of $R(x)$ will come later, but right now we can kind of write this incomplete formula.
$$
{ax^p + ...\over bx^d + ...} = cx^{p-d} + ... + R(x)
$$

## Representing Polynomial Multiplication as a Linear Transformation

So if you're familiar with vector spaces you probably are aware we can represent polynomials as vectors.
$$
ax^2+bx+c \implies
\text{span}\left\{
    \begin{bmatrix}
    x^2\\0\\0
    \end{bmatrix},
    \begin{bmatrix}
    0\\x\\0
    \end{bmatrix},
    \begin{bmatrix}
    0\\0\\1
    \end{bmatrix},
\right\}
$$
We can also take polynomials to be dot products between our vector of $x$ terms and a vector of coefficients.
$$
2x^2+3x-4 =
\begin{bmatrix}
    2&3&-4
\end{bmatrix}
\begin{bmatrix}
    x^2\\x\\1
\end{bmatrix}
=
\left(\begin{bmatrix}
    2\\3\\-4
\end{bmatrix}\right)^T
\begin{bmatrix}
    x^2\\x\\1
\end{bmatrix}
$$

Now let's try multiplying two polynomials:
$$
(ax+b)(Ax^2+Bx+C) = aAx^3 + (aB+bA)x^2 + (aC+bB)x + bC
$$
This forms a linear system of equations in our coefficients, and any time we can form a linear system of equations we can represent it as a matrix transformation:
$$
\begin{bmatrix}
    A&0\\
    B&A\\
    C&B\\
    0&C
\end{bmatrix}
\begin{bmatrix}
    a\\b
\end{bmatrix}
=
\begin{bmatrix}
    aA\\
    aB+bA\\
    aC+bB\\
    bC
\end{bmatrix}
$$
we can also do this the other way around.
$$
\begin{bmatrix}
    a&0&0\\
    b&a&0\\
    0&b&a\\
    0&0&b
\end{bmatrix}
\begin{bmatrix}
    A\\B\\C
\end{bmatrix}
=
\begin{bmatrix}
    aA\\
    aB+bA\\
    aC+bB\\
    bC
\end{bmatrix}
$$
And if we can recall our dot product representation:
$$
(aA)x^3 + (aB+bA)x^2 + (aC+bB)x + bC
=
\left(
\begin{bmatrix}
    aA\\
    aB+bA\\
    aC+bB\\
    bC
\end{bmatrix}
\right)^T
\begin{bmatrix}
    x^3\\x^2\\x\\1
\end{bmatrix}
$$
Factoring out our matrix we get two different matrix products to represent the same polynomial:
$$
P(x)=
\begin{bmatrix}
    A&B&C
\end{bmatrix}
\begin{bmatrix}
    a&b&0&0\\
    0&a&b&0\\
    0&0&a&b
\end{bmatrix}
\begin{bmatrix}
    x^3\\x^2\\x\\1
\end{bmatrix}
=
\begin{bmatrix}
    a&b
\end{bmatrix}
\begin{bmatrix}
    A&B&C&0\\
    0&A&B&C
\end{bmatrix}
\begin{bmatrix}
    x^3\\x^2\\x\\1
\end{bmatrix}
$$
For those familiar with quadratic forms this representation might not be new to you.

Now if you notice, this matrix is not invertible as it's a rectangular matrix. So we can't simply find an inverse matrix for multiplication. That said however, we can employ a little trick that just might give us something invertible.

## Creating an Invertible Matrix

So let's take the same polynomial multiplication, but I'm going to add some arbitraty polynomial $R(x)$ to our product:
$$
(ax+b)(Ax^2+Bx+C) + R(x) = aAx^3 + (aB+bA)x^2 + (aC+bB)x + bC + R(x)
$$
Now I'm going to chose $R(x)$ to be so:
$$
R(x) = Rr_1x + r_2
$$
Now I will add it to our product:
$$
(ax+b)(Ax^2+Bx+C)+r_1x+r_2 = aAx^3 + (aB+bA)x^2 + (aC+bB+r_1)x + (bC+r_2)
$$
This gives us an updated system of equations, let's try turning it into a matrix transformation:
$$
\begin{bmatrix}
    A&0&0&\\
    B&A&0&0\\
    C&B&1&0\\
    0&C&0&1
\end{bmatrix}
\begin{bmatrix}
    a\\b\\r_1\\r_2
\end{bmatrix}
=
\begin{bmatrix}
    aA\\
    aB+bA\\
    aC+bB+r_1\\
    bC+r_2
\end{bmatrix}
$$
Now wait a second, this matrix is lower triangular. Which means it is **invertible**!!!

So let's try dividing our polynomial
$$
\begin{aligned}
    {aAx^3 + (aB+bA)x^2 + (aC+bB+r_1)x + (bC+r_2)\over Ax^2+Bx+C} = ax+b + {r_1+r_2\over Ax^2+Bx+C}\\
    {aAx^3 + (aB+bA)x^2 + (aC+bB)x + (bC+r)\over ax+b} = Ax+B+C + {r\over ax+b}
\end{aligned}
$$
Notice I modified $R(x)$ in the second equation, this will make more sense later.

So now we have found two invertible matrices that can represent this polynomial product with addition by this arbitrary $R(x)$.
$$
\begin{aligned}
\begin{bmatrix}
    A&0&0&\\
    B&A&0&0\\
    C&B&1&0\\
    0&C&0&1
\end{bmatrix}
\begin{bmatrix}
    a\\b\\r_1\\r_2
\end{bmatrix}\\
\begin{bmatrix}
    a&0&0&0\\
    b&a&0&0\\
    0&b&a&0\\
    0&0&b&1
\end{bmatrix}
\begin{bmatrix}
    A\\B\\C\\r
\end{bmatrix}
\end{aligned}
$$

Let's take a step back and think about what we did, we just took the expression:
$$
D(x)Q(x) + R(x)
$$
and turned it into an invertible matrix expression.

If we think about what this means, we can actually represent this polynomial division:
$$
{Px^3 + Qx^2 + Rx +S\over ax+b} = (Ax^2+Bx+C) + {r\over ax+b}
$$
into two matrix forms:
$$
\begin{bmatrix}
    a&0&0&0\\
    b&a&0&0\\
    0&b&a&0\\
    0&0&b&1
\end{bmatrix}
\begin{bmatrix}
    A\\B\\C\\r
\end{bmatrix}
=
\begin{bmatrix}
    P\\Q\\R\\S
\end{bmatrix}
\qquad
\begin{bmatrix}
    {1\over a}&0&0&0\\
    -{b\over a^2}&{1\over a}&0&0\\
    {b^2\over a^2}&-{b\over a^2}&{1\over a}&0\\
    -{b^3\over a^3}&{b^2\over a^2}&-{b\over a}&1
\end{bmatrix}
\begin{bmatrix}
    P\\Q\\R\\S
\end{bmatrix}
=
\begin{bmatrix}
    A\\B\\C\\r
\end{bmatrix}
$$

And the same with the other factor:
$$
\begin{aligned}
    {Px^3 + Qx^2 + Rx +S\over Ax^2+Bx+C} &= (ax+b) + {r_1x+r_2\over Ax^2+Bx+C}\\
    \begin{bmatrix}
        A&0&0&0\\
        B&A&0&0\\
        C&B&1&0\\
        0&C&0&1
    \end{bmatrix}
    \begin{bmatrix}
        a\\b\\r_1\\r_2
    \end{bmatrix}
    =
    \begin{bmatrix}
        P\\Q\\R\\S
    \end{bmatrix}
    &\qquad
    \begin{bmatrix}
        {1\over A}&0&0&0\\
        -{B\over A^2}&{1\over A}&0&0\\
        {b^2-AC\over A^2}&-{B\over A}&1&0\\
        -{bC\over A^2}&-{C\over A}&0&1
    \end{bmatrix}
    \begin{bmatrix}
        P\\Q\\R\\S
    \end{bmatrix}
    =
    \begin{bmatrix}
        a\\b\\r_1\\r_2
    \end{bmatrix}
\end{aligned}
$$

So essentially, the degree of the remainder is just large enough to allow us to construct a square matrix. If you take a look at our matrix you'll see that it's rows are one more than the degree of p, and the columns are the degree of q and r and 2.
$$
(p+1)\times(q+r+2)
$$
And since we know that the degree of $Q(x)$ can be written in terms of $D(x)$ and $P(x)$ we can find that the degree of $R(x)$ is one less than the degree of $D(x)$:
$$
\begin{aligned}
    (p+1)&\times(p-d+r+2)\\
    (p+1)&\times(p+1+r-d+1)\\
    \implies r-d+1 &= 0\\
    \therefore~r&= d-1
\end{aligned}
$$


## Notes on generality

For simplicity I focused on a single example, but there was nothing special about this particular example and we can continue this formulation for polynomials of higher degree too.

Although I will admit that I haven't proven that we can do this for **all** polynomials, but I think that's okay since the only times I've actually needed to use this have been for matrices with relatively small degrees, as much as 8 in some cases. And it hasn't failed me yet. Perhaps with polynomials with very large degrees this breaks down, or maybe if the coefficients aren't real numbers or your in some other field. However I have a feeling that this will still hold for those systems as well, although proving it is beyond the scope of this video and beyond my current motivations.

Perhaps another time I will go through and work this out, but for now I think this is just a cool concept.

## Full Algorithm

So now it's time to take a look at the full algorithm.

1. Create a general polynomial $Q(x)$ with degree $p-d$
2. Create a general polynomial $R(x)$ with degree $d-1$
3. Create the multiplication matrix for $D(x)Q(x)$
4. Extend the matrix with diagonal ones to make it square.
   - The number of ones depends on $R(x)$
5. Invert the matrix
6. Turn $P(x)$ into a vector in $\mathbb{R}^{p+1}$
7. Multiply $\vec{P}$ by the inverse matrix.

Steps 1,2,4,6 don't require a lot of effort to do and the main time crunch will be spent on steps 3 and 5.

Step 7 can be done by a computer.

However I will show you a method that will simplify these steps into one single calculation.

## A nice way to generate the matrix

So to generate the inverse, we first want a very simple way to generate the original matrix.

One thing you'll notice as you create many of these is that there is a very simple pattern in how these are created.

To generate the matrix, simply create one column for every coefficient in $Q(x)$. This will be $\deg Q(x)+1$ columns.
$$
\begin{bmatrix}
    0&0\\
\end{bmatrix}
$$
Then write down all the coefficients of $D(x)$ in each column starting from the top, then on every column shift them down. Then add zeros everywhere else.
$$
\begin{bmatrix}
    a&0\\
    b&0\\
    c&0
\end{bmatrix}
\implies
\begin{bmatrix}
    a&0\\
    b&a\\
    c&b\\
    0&c
\end{bmatrix}
$$
Finally add the required amount of ones.
$$
\begin{bmatrix}
    a&0&0&0\\
    b&a&0&0\\
    c&b&1&0\\
    0&c&0&1
\end{bmatrix}
$$

## A nice way to generate the inverse

Now if the matrix can be done in such a simple pattern, then you bet the inverse can be done in a simple pattern as well.

Since the matrix is diagonal we just invert each column. Starting with the first.
$$
\begin{bmatrix}
    {1\over a}\\
    -{b\over a}\\
    -{c\over a}\\
\end{bmatrix}
\implies
\begin{bmatrix}
    {1\over a}&0\\
    -{b\over a^2}&{1\over a}\\
    {b^2-ac\over a^2}&-{b\over a}\\
    {bc\over a^2}&-{c\over a}
\end{bmatrix}
$$
Then we add the ones
$$
\begin{bmatrix}
    {1\over a}&0&0&0\\
    -{b\over a^2}&{1\over a}&0&0\\
    {b^2-ac\over a^2}&-{b\over a}&1&0\\
    {bc\over a^2}&-{c\over a}&0&1
\end{bmatrix}
$$

If you actually stop to think about it, we don't actually need to know the original matrix, we could have just generated the inverse first the same way we made the original matrix. Except every time we create a new column, we apply the relevant tranformation to the previous matrices. For computational purposes this could help use save space and time making the first matrix.

## Formulas,

Now if we look at the inverse matrix we may notice that we could write the transformation as a linear system of equations for our coefficients as well. If we do that we will actually end up with some interesting formulas for dividing two polynomials.

I took the liberty of writing these down, I hope you like them.

Here's a formula when dividing a degree 1 polynomial
$$
\begin{aligned}
    {Ax+B\over ax+b} &= {1\over a}\left(A+{aB-bA\over ax+b}\right)\\
\end{aligned}
$$
Here are formulas for dividing a degree 2 polynomial
$$
\begin{aligned}
    {Ax^2+Bx+C\over ax+b} &= {1\over a^2}\left(aAx+(aB-bA)+ {a^2X+b^2A-baB\over ax+b}\right)\\
    {Ax^2+Bx+C\over ax^2+bx+c} &= {1\over a}\left(A+{(aB-bA)x+(aC-cA)\over ax^2+bx+c}\right)
\end{aligned}
$$

Here are formulas for dividing a degree 3 polynomial
$$
\begin{aligned}
    {Ax^3+Bx^2+Cx+D\over ax+b} &= {1\over a^2}\left(a^2Ax^2+(a^2B-bA)x+(a^2C-baB+b^2A)+{a^2D-ba^2C+b^2aB-b^2A\over ax+b}\right)\\
    {Ax^3+Bx^2+Cx+D\over ax^2+bx+c} &= {1\over a^2}\left(aAx+(aB-bA)+{(a^2C-baC+(b^2-ca)A)x+(a^2D-caB+bcA)\over ax^2+bx+c}\right)\\
    {Ax^3+Bx^2+Cx+D\over ax^3+bx^2+cx+d} &= {1\over a}\left(A + {(aB-bA)x^2+(aC-cA)x+(aD-dA)\over ax^3+bx^2+cx+d}\right)\\
\end{aligned}
$$

If you notice dividng two equal degree polynomials forms a pattern, and it's here where I device this conjecture:
$$
{\displaystyle\sum^n_{i=0}A_ix^i\over\displaystyle\sum^n_{i=0}a_ix^i} = {1\over a_n}\left(A_n+{\displaystyle\sum^{n-1}_{i=0}(a_nA_i-a_iA_n)x^i\over\displaystyle\sum^n_{i=0}a_ix^i}\right)
$$
I haven't proved this, but it seems to be the case for the polynomials I have tested. I'm curious what everyone thinks and I'll maybe try proving it some other time.

Another thing I noticed was that the coefficients seemed to follow some sort of combinatorial pattern, I have had a few ideas but haven't been able to generalize it fully yet. I wonder what this could mean for a more generalized notion of division.

If anyone knows more about this feel free to let me kknow in the comments.

## Examples

This lesson wouldn't be complete without some examples so let's go at it:

### Example 1

Let's try this first example:
$$
{3x^3+4x^2+2x-1\over2x^2-3x+4}
$$
Let's make the matrix:
$$
\begin{bmatrix}
    2&0&0&0\\
    -3&2&0&0\\
    4&-3&1&0\\
    0&4&0&1
\end{bmatrix}
$$
Now invert and multiply
$$
\begin{bmatrix}
    {1\over2}&0&0&0\\
    {3\over4}&{1\over2}&0&0\\
    {1\over4}&{3\over2}&1&0\\
    -3&-2&0&1
\end{bmatrix}
\begin{bmatrix}
    3\\4\\2\\-1
\end{bmatrix}
\begin{bmatrix}
    {3\over2}\\
    {17\over4}\\
    {35\over4}\\
    -18
\end{bmatrix}
=
\begin{bmatrix}
    A\\B\\r_1\\r_2
\end{bmatrix}
$$
so here's the solution:
$$
{3x^3+4x^2+2x-1\over2x^2-3x+4} = {3\over2}x+{17\over4}+{{35\over4}x-18\over2x^2-3x+4}
$$
Do you see how simple this is?

### Example 2

Let's try this one:
$$
{4x^4+3x^3+x-4\over3x^3-5x^2-2x+3}
$$
We make the matrix:
$$
\begin{bmatrix}
    3&0&0&0&0&0\\
    -5&3&0&0&0&0\\
    -2&-5&3&0&0&0\\
    3&-2&-5&1&0&0\\
    0&3&-2&0&1&0\\
    0&0&3&0&0&1
\end{bmatrix}
$$
And invert and multiply:
$$
\begin{bmatrix}
    {1\over3}&0&0&0&0&0\\
    {5\over9}&{1\over3}&0&0&0&0\\
    {31\over27}&{5\over9}&{1\over3}&0&0&0\\
    {158\over27}&{31\over9}&{5\over3}&1&0&0\\
    {17\over27}&{1\over9}&{2\over3}&0&1&0\\
    -{31\over9}&-{5\over3}&-1&0&0&1
\end{bmatrix}
\begin{bmatrix}
    4\\0\\3\\0\\1\\-4
\end{bmatrix}
=
\begin{bmatrix}
    {4\over3}\\
    {20\over9}\\
    {151\over27}\\
    {767\over27}\\
    {149\over27}\\
    {-187\over9}
\end{bmatrix}
$$
And here's our solution:
$$
{4x^4+3x^3+x-4\over3x^3-5x^2-2x+3} = {4\over3}x^2+{20\over9}x+{151\over27}+{{767\over27}x^2+{149\over27}x-{187\over9}\over3x^3-5x^2-2x+3}
$$

### Example 3

Let's try another example:
$$
{2x^2-5x-12\over3x-6}
$$
Let's try the formula this time:
$$
\begin{aligned}
    {P(x)\over D(x)} &= {1\over 9}\left(6x+(-15+12)+{9(-12)+(36)2-(-6)(3)(-5\over3x-6)}\right)\\
    &= {1\over9}\left(6x-3-{126\over3x-6}\right)\\
    &= {2\over3}x-{1\over3}-{14\over3x-6}
\end{aligned}
$$

### Example 4

Let's try this example:
$$
{4x^5+3x^2-2\over3x^5+2x^4-3x^3+x}
$$
Let's use the formula for equal powers:
$$
\begin{aligned}
    {P(x)\over D(x)} &= {1\over3}\left(4+{(3\cdot0-3\cdot2)x^4+(3\cdot0-4(-3))x^3+(3\cdot3-4\cdot0)x^2+(3\cdot0-4\cdot1)x+(3(-2)-3\cdot0)\over3x^5+2x^4-3x^3+x}\right)\\
    &= {1\over3}\left(4+{-8x^4+12x^3+9x^2-4x-6\over3x^5+2x^4-3x^3+x}\right)
\end{aligned}
$$

## Conclusion

To conclude, this isn't a very rigorous theory. But I do think it's a helpful tool for most cases when you might do polynomial division by hand.

As you can see there are still some open questions in regards to the structure of these equations, and I hope to tackle them soon. If anyone else wants to give them a go in the comments or at home please feel free. I'm curious what you all come up with and whether or not we can find more patterns in this.

As for my channel, I'm still trying to figure out what to do with it and I'm planning on making some more math meme content. My current goal is to have a channel like the old school game theory that would mix science and gaming in an educational way. I miss those kinds of videos and was hoping that I could try to revive that.

Feel free to like and subscribe for more!
