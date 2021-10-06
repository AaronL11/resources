\newpage

# Partial Differentiation

We are already familiar with derivatives for single variable functions. When we take 

We use $\partial$ instead of $d$ to denote a partial derivative.

For example:
$$
f(x,y) = x\cos y
$$
We then find the two partial derivatives:
$$
\begin{aligned}
    {\partial f\over\partial x} &= \cos y\\
    {\partial f\over\partial y} &= -x\sin y\\
\end{aligned}
$$

Partial Derivatives also use all the rules of normal derivatives.

## Generalized Chain Rule

The chain rule however works a little different in multiple dimensions.

Let's review the single variable case:
$$
(g\circ f)'(x) = g'(f(x))f'(x)
$$

$$
{d\over dx}\left[g\big(f(x,y)\big)\right] = {d\over dx}g\big(f(x,y)\big)\cdot{\partial\over\partial x}f(x,y)
$$
We can do the same for ${d\over dy}g$. 

To see the more general case of a multivariable function we will use the following example:
$$
F(s,t) = f(x,y)
$$
Where $x$ and $y$ are function of $s$ and $t$. Or in other words:
$$
F\big(x(s,t),y(s,t)\big)
$$
We can then take the chain rule as the sum of our previous chain rules:
$$
{\partial F\over\partial t} = {\partial f\over\partial x}{\partial x\over\partial t} + {\partial f\over\partial y}{\partial y\over\partial t}
$$
The same works for $\partial F\over\partial s$ as well as for deeper function compositions and more variables.

## Tangent Planes

When we draw single variable functions, we know we can draw another line as the slope of that function. This is the tangent line of our function:
$$
y = f'(a)(x-a) + f(a)
$$

With multi variable functions we can do this for multiple variables. Each partial derivative gives us a new line.

Since we have two lines intersecting, we can form a plane between them. This is called a **Tangent Plane**.

Essentially the tangent plane is the span of the slope of the vectors formed from our partial derivatives:
$$
T=\text{span}\left\{{\partial f\over\partial x},{\partial f\over\partial y}\right\}
$$

## Gradient



## Laplacian

$$
\Delta^2f
$$

## Lagrange Multipliers

$$
\begin{aligned}
    \nabla f = \lambda\nabla g\\
    g = 0
\end{aligned}
$$
