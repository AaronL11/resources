\newpage

# Differentiation

## Definition of the Derivative

$$
\lim_{h\rightarrow0}{f(x+h)-f(x)\over h}
$$

### Other Notations

### Linearity of the Derivative

$$
{d\over dx}[af(x)+bg(x)] = a{d\over dx}[f(x)] + b{d\over dx}[g(x)]
$$
We will prove this in the next section.

## Derivative Rules

### Scaling

$$
\begin{aligned}
    {d\over dx}[cf(x)] &= \lim_{h\rightarrow0}{cf(x+h)-cf(x)\over h}\\
    &= \lim_{h\rightarrow0}~c\left(f(x+h)-f(x)\over h\right)\\
    &= c\cdot\lim_{h\rightarrow0}{f(x+h)-f(x)\over h}\\
    &= c{d\over dx}f(x)
\end{aligned}
$$

$$
{d\over dx}[cf(x)] = c{d\over dx}f(x)
$$

### Addition Rule

$$
\begin{aligned}
    {d\over dx}[f(x)+g(x)] &= \lim_{h\rightarrow0}{[f(x+h)+g(x+h)]-[f(x)+g(x)]\over h}\\
    &= \lim_{h\rightarrow0}{f(x+h)-f(x)\over h} + \lim_{h\rightarrow0}{g(x+h)-g(x)\over h}\\
    &= {d\over dx}f(x) + {d\over dx}g(x)
\end{aligned}
$$

$$
{d\over dx}[f(x)+g(x)] = {d\over dx}f(x) + {d\over dx}g(x)
$$

These two rules are all we need to prove linearity of the derivative.

### Product Rule

$$
{d\over dx}[f(x)g(x)] = g(x){d\over dx}f(x) + f(x){d\over dx}g(x)
$$

### Quotient Rule

$$
{d\over dx}\left[f(x)\over g(x)\right] = {g(x){d\over dx}f(x) - f(x){d\over dx}g(x)\over g^2(x)}
$$

### Chain Rule

$$
(f\circ g)(x) = f\big(g(x)\big)
$$

$$
(f\circ g)'(x) = f'\big(g(x)\big)\cdot g'(x)
$$

## Higher Order Derivatives

## Derivatives of Elementary Functions

### Power Rule

A big key for understanding the derivatives of elementary functions is a rule called the **Power Rule**.

To see how this rule works let's try to take the following derivative $f(x) = x^n$:
$$
\begin{aligned}
    {d\over dx}\left[x^n\right] &= \lim_{h\rightarrow0}{(x+h)^n-x^n\over h}\\
    &= \lim_{h\rightarrow0}{x^n + nx^{n-1}h + ... + C_kh^k + ... h^n -x^n\over h}\\
    &= \lim_{h\rightarrow0}{nx^{n-1}h + ... + C_kh^k + ... + h^n\over h}\\
    &= \lim_{h\rightarrow0}nx^{n-1} + ... + C_kh^{k-1} + ...+ h^{n-1}\\
    &= nx^{n-1} + 0
\end{aligned}
$$

This gives us our general formula for the power rule.
$$
{d\over dx}\left[x^n\right] = nx^{n-1}
$$

If we set $x$ to be some arbitrary function $f(x)$ (where $f$ is continous and differentiable), we can use the chain rule to take derivatives of more complex functions:
$$
{d\over dx}\left[f^n(x)\right] = nf^{n-1}(x){d\over dx}f(x)
$$

### Constant Function

Since a constant function $f(x) = c$ doesn't change (since it's the same value for all $x$), then we can declare that it's derivative is zero. However it is probably a good idea to make sure this matches what our derivative formula spits out.
$$
{d\over dx}[c] = \lim_{h\rightarrow0}{f(x+h) - f(x)\over h} = \lim_{h\rightarrow0}{c-c\over h} = 0
$$

This matches our intuition nicely.
$$
{d\over dx}[c] = 0
$$

### Polynomials

A polynomial is simply a sum of powers of $x$:
$$
a_0 + a_1x + a_2x^2 + ... + a_nx^n
$$

We simply apply the addition rule, and then the scaling rule, and then we can apply the power rule!
$$
\begin{aligned}
    {d\over dx}\left[a_0 + a_1x + ... + a_nx^n\right]
    &=
    {d\over dx}\left[a_1\right] + {d\over dx}\left[a_1x\right] + ... + {d\over dx}\left[a_nx^n\right]\\
    &= 0 + a_1 + ... + a_kkx^{k-1} + ... + a_nnx^{n-1}
\end{aligned}
$$
Notice how the power decreases. If we were to take higher order derivatives continoually, eventually we would hit 0:
$$
\begin{aligned}
    {d\over dx}\left[x^n\right] &= nx^{n-1}\\
    {d^2\over dx^2}\left[x^n\right] &= n(n-1)x^{n-2}\\
    &\vdots\\
    {d^k\over dx^k}\left[x^n\right] &= {n!\over(n-k)!}x^{n-k}\\
    {d^n\over dx^n}\left[x^n\right] &= n!\\
    {d^{n+1}\over dx^{n+1}}\left[x^n\right] &= 0\\
\end{aligned}
$$

### Rationals

Let's think of a simple rational function:
$$
f(x) = {1\over x} = x^{-1}
$$
Since rational functions are equivalent to functions raised to negative powers then this is simply another version of the power rule!

$$
\begin{aligned}
    {d\over dx}\left[x^{-n}\right] &= -nx^{-(n+1)}\\
    {d\over dx}\left[1\over x\right] &= -{n\over x^{n+1}}
\end{aligned}
$$

Interestingly, the derivative of a rational function is a rational function raised to a higher power. This means we could take derivatives of rational functions continually as they don't converge to 0 like derivatives of positive powers.

$$
\begin{aligned}
    {d\over dx}\left[1\over x^n\right] &= -{n\over x^{n+1}}\\
    {d^2\over dx^2}\left[1\over x^n\right] &= {n(n+1)\over x^{n+2}}\\
    &\vdots\\
\end{aligned}
$$

### Radicals

Once again, we can express radicals as powers.
$$
\sqrt[n]{x} = x^{1\over n}
$$
This means we only need to apply the power rule
$$
\begin{aligned}
    {d\over dx}\left[x^{1\over n}\right] &= {1\over n}x^{{1\over n}- 1} = {1\over n}x^{-\left(n-1\over n\right)}\\
    {d\over dx}\left[\sqrt[n]{x}\right] &= {1\over n\sqrt[n]{x^{n-1}}}
\end{aligned}
$$

### Trigonometric

$$

$$

### Hyperbolic

$$

$$

### Exponential

## Derivatives of Inverse Functions

### Inverse Trigonometric

### Inverse Hyperbolic

### Inverse Logarithmic

## Approximating Derivatives

### Newton's Method

## Antidifferentiation
