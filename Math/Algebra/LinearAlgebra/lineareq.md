\newpage

# Linear Systems of Equations

## A simple Linear Equation

So to begin, what is a linear equation?

Well let's think about a 2D line in space. How can we describe this line algebraicly? Right away we can notice that the line crosses our $y$ and $x$ axis only once, and extends off to the edge of our plane and beyond on either side. We can also see that the line has unique $x$ and $y$ positions.

Let's take 2 points in our $x$ axis and slightly increase them by a small factor. If you notice, the distance between our $y$ values remains the same as it was in our original points. Additionally, there's nothing special here about the points we chose. No matter where we take these 2 $x$ values, any changes in them will always result in thesame change in the corresponding $y$ values since the line will never curve.

This is in contrast to what we can consider non-linear, where as we change our $x$, the $y$ value will increase or decrease and the distance between two $y$ values will vary throughout the entire line.

So given what we now know from quickly analysing the geometry we can come to form some algebraic description of our line. To do this we're going to have to create some reference for our line to begin, to make things simpler I'll draw in some numbers, and we'll say that our line will start when $x=0$. Which in this case is 3. We now take the factor that governs our change in $y$ for every change in $x$. This will be our slope and we can find it by taking the ratio of the change in both $y$ and $x$. This gives us a slope of 2. Now to verify that this is the equation of our line we can take any number in $x$ and then verify that the corresponding $y$ wil place us on our line.

We can do this same process for multiple lines to check if this works for all lines, but essentially every line we can draw in two dimensions will have this form:
$$
y = ax+b
$$

We could have also done this with $y=0$ as our origin and we would have found the equation:
$$
x = {y\over2}-{3\over2}
$$
However if we really think about it, this is still in the same form of $y=ax+b$, since the variables we pick are kind of arbitrary.

### Linearity

The property that graphically represents a straight line is called linearity. A relationship between two things is called linear if it satisfies the property of linearity. Which looks something like:
$$
\begin{aligned}
    L(x+y) &= L(x)+f(y)\\
    L(kx) &= kL(x)
\end{aligned}
$$

### Standard and General Form

Let's take our equation again:
$$
y = ax+b
$$
and adjust it so all our variables are on one side:
$$
-ax+y = b
$$
This is called the **standard form** for our equation.

If we adjust this some more:
$$
-ax + y -b = 0
$$
This is called the **general form** of our equation.

Both of these equations represent the same line, and we can say more generally that any equation that any relationship that can be written like this must represent a single line through space.



## Multiple Variables

Let's take a moment to think about what each variable tells us about the dimension we're working with. A single $x$ variable kind of represents a point in space doesn't it?
$$
ax+b = 0
$$
There is only one solution to this problem. And that's $x=-\tfrac{b}{a}$, so the space of solutions to this equation represents only a single point.

Now when we add a 2nd variable $y$ our equation looks like this:
$$
ax + by + c = 0
$$
And we've already shown that the space that represents the solutions to these equations gives us a line.

Now let's think about what happens if we add one more variable $z$:
$$
ax + by + cz + d = 0
$$
$$
z = -{a\over c}x - {b\over c}y - {d\over c}
$$
If we set both variables to $0$, we find a single point $-\tfrac{d}{c}$, we also should keep in mind that we want we want our $c$ to not be 0. If we start from this point, and start only with our $x$ we'll find that we create a line. If we then set $x$ as 0 and traverse $y$ we find another line. Geometrically as we travel along both lines we essentially fill in a plane in 3D space. This equation in 3 variables represents a 2D plane.

We could also continue this for 4 variables.
$$
ax + by + cz +dw + e = 0
$$
However the same logic will apply and it's sort of difficult to visualize, but essentially we would have some 3 dimensional object embedded in 4D space being represented here. We can continue this pattern for even more variables as well!. Taking only this basic intuition that we've just discovered, that is every linear equation is formed from smaller singular linear equations representing lines. In essence it's anything with the following form:
$$
a_1x_1+...+a_nx_n+b=0
$$

### Systems of Linear Equations

Once we start grouping multiple linear equations with the same variables, we get what is called a **system of linear equations**

This is an example of a system of linear equations with 3 equations and 3 variables in general form:
$$
\begin{aligned}
    2x -4y +5z -5 &= 0\\
    -3x +5y +1z -4 &= 0\\
    -1x -1y + 4z -6 &= 0
\end{aligned}
$$
If you remember we can write this system in standard form like so:
$$
\begin{aligned}
    2x -4y +5z &= 5\\
    -3x +5y +1z &= 4\\
    -1x -1y + 4z &= 6
\end{aligned}
$$
It's important to remember that every $x$, $y$, and $z$ in each equation refer to 3 unique numbers that are present in all those equations that will make the equations true.

Some examples of other linear systems of $n$ equations and $m$ variables $E_{nm}$ in general form:
$$
{\small\begin{aligned}
    E_{22} &=
    \begin{aligned}
        4x+3y+5&=0\\
        7x-2y-3&=0
    \end{aligned}
    \qquad
    E_{32} =
    \begin{aligned}
        4x+5y-3&=0\\
        5x-6y+0&=0\\
        -2x-4y-6&=0
    \end{aligned}\\
    E_{56} &=
    \begin{aligned}
        1x-8y+7z-2w+3i+4j+2&=0\\
        5x+2y+5z+1w+7i-8j-4&=0\\
        3x-5y+2z+4w+3i+1j+5&=0\\
        2x-4y+3z-2w+2i-3j-3&=0\\
        6x+1y+8z-9w+2i-4j+7&=0\\
    \end{aligned}
\end{aligned}}
$$
Try to think about what these represent geometrically!

So now that we've finished defining what a linear equation *is*, we can't really do much with them at the moment. Part of this conundrum happens because we aren't quite sure how to solve these systems, and what their solutions even represent.

## Solving Systems of Linear Equations

Let's take the following system of equations:
$$
\begin{aligned}
    x - y + 2z &= 11\\
    2y -z &= 2\\
    3x-2y+2z &= 13
\end{aligned}
$$
Let's think about how we can solve this system, in other words what $x$, $y$ and $z$ satisfy this equation?

To aid us in this struggles I will be labeling each equation like so:
$$
\begin{aligned}
    E_1(x,y,z) &= 1x - 1y + 2z = 11\\
    E_2(x,y,z) &= 0x + 2y -1z = 2\\
    E_3(x,y,z) &= 3x-2y+2z = 13
\end{aligned}
$$
Remember linearity, we can formulate this as a linear equation with $ax+b$, where $b$ is just another equation.
$$
E_1(x,y,z) = x + E_1(y,z) = 11
$$
Notice that equation 3 also has this similar structure with a non-zero coefficient for $x$ and addition of another linear equation in $y$ and $z$.
$$
E_3(x,y,z) = 3x + E_3(y,z) = 13
$$
Now we're going to subtract one equation from the other. This will remove the $x$ variables in our equation.
$$
3x +E_3(y,z) - 3(x + E_1(y,z)) = 13-33
$$
We can rewrite this in terms of our equations $E_1$ and $E_3$ as:
$$
E_3(x,y,z) - 3E_1(x,y,z) = 13-33
$$
The act of eliminating our equations like this is called **Gauss-Jordan Elimination**.

I'm going to remove the parameters to make things easier to read. It will also come in handy later to make sure we mark down the operations we are doing and their equations. So I'll put that off to the side.
Now if you notice this creates a brand new set of equations, that are still just as true as the previous system.
$$
\begin{aligned}
    x - y +2z &= 11\\
    2y-z&=2\\
    y-4z &= -20
\end{aligned}
\quad
E_3\rightarrow E_3-3E-1
$$
Using what we've just used we can continue to adjust our system of equation writing down all the operations we do between those equations. We will continue this process of adding and subtracting equations until we have a single variable per line:
$$
\begin{aligned}
    x-y+2z &= 11\\
    2y-z - (2y-4z) &= 2+40\\
    y-4z &= -20\\
    \\
    x-y+2z &= 11\\
    7z\div7&= 42\div7\\
    y-4z &= -20\\
    \\
    x-y+2z &= 11\\
    y-4z &= -20\\
    z &= 6\\
    \\
    x-y+2z &= 11\\
    y-4z+4z &= -20+24\\
    z &= 6\\
    \\
    x-y+2z + y -2z &= 11 +4 - 12\\
    y &= 4\\
    z &= 6
\end{aligned}
\quad
\begin{aligned}
    \\
    E_2&\rightarrow E_2 - 2E_3\\
    \\
    \\
    \\
    E_2&\rightarrow E_2/7\\
    \\
    \\
    \\
    E_2&\leftrightarrow E_3\\
    \\
    \\
    \\
    E_2&\rightarrow E_2+4E_3\\
    \\
    \\
    \\
    E_1&\rightarrow E_1 + E_2 - 2E_3\\
    \\
\end{aligned}
$$
At the end we've arrived at our solution:
$$
\begin{aligned}
    x&=3\\y&=4\\z&=6
\end{aligned}
$$
And the operations we did to get there are:
$$
\begin{aligned}
    E_3 &\rightarrow E_3-3E_1,\\
    E_2 &\rightarrow E_2-2E_3,\\
    E_2 &\rightarrow E_2/7,\\
    E_2&\leftrightarrow E_3,\\
    E_3 &\rightarrow E_3+4E_2\\
    E_1 &\rightarrow E_1+E_3-2E_2
\end{aligned}
$$
If we notice something, in our final system of linear equations, $x=3$ was our first equation, $y=4$ our second and $z=6$ our third. By substituting our final versions of $E_1,E_2,E_3$ for $x,y,z$ respectively we end up with the following system of equations were the variables are our original starting equations:
$$
\begin{aligned}
    x &= E_1 + E_3 - 3E_1 + {4\over7}(E_2-2(E_3-3E_1)) - {2\over7}(E_2-2(E_3-3E_1))\\
    y &= E_3-3E_1 + {4\over7}(E_2-2(E_3-3E_1))\\
    z &= {E_2-2(E_3-3E_1)\over7}
\end{aligned}
$$
Let's organize this a little bit:
$$
\begin{aligned}
    x &= -{2\over7}E_1+{2\over7}E_2 + {3\over7}E_3\\
    y &={3\over7}E_1 + {4\over7}E_2 -{1\over7}E_3\\
    z &= {6\over7}E_1 + {1\over7}E_2 - {2\over7}E_3
\end{aligned}
$$
Isn't it a bit odd that this $\tfrac{1}{7}$ appears in every term? This isn't just a coincidence, there is a reason for this however we will discuss this much later.

One thing that becomes immediatly apparent however, is that we have been able to write $x$,$y$ and $z$ in terms of linear equations. Now keep in mind that if we look back to when we started, these linear equations actualy had values:
$$
\begin{aligned}
    E_1&=11\\
    E_2&=2\\
    E_3&=13
\end{aligned}
$$
Let's try changing these values, how about $E_1=E_2=E_3=7$:
$$
\begin{aligned}
    x &= -{2\over7}7+{2\over7}7 + {3\over7}7\\
    y &={3\over7}7 + {4\over7}7 -{1\over7}7\\
    z &= {6\over7}7 + {1\over7}7 - {2\over7}7
\end{aligned}
~{\huge\rightarrow}~
\begin{aligned}
    x &= -2+2 + 3\\
    y &=3 + 4 -1\\
    z &= 6 + 1 - 2
\end{aligned}\\
\begin{aligned}
    x&=3\\
    y&=6\\
    z&=5
\end{aligned}
$$
Let's plug this in to our original system just to see if this adds up:
$$
\begin{aligned}
    E_1&\rightarrow\\
    E_2&\rightarrow\\
    E_3&\rightarrow
\end{aligned}
\quad
\begin{aligned}
    (3) - (6) + 2(5) &= 10-3\\
    2(6) -(5) &= 12-5\\
    3(3)-2(6)+2(5) &= 9-2
\end{aligned}\\
E_1=E_2=E_3=7
$$
If our original system of equations $E$ is a function that takes 3 numbers $(x,y,z)$ to 3 new numbers $(a,b,c)$, then this new system of equations $F$ will take our numbers $(a,b,c)$ and return the $(x,y,z)$ that formed them.
$$
\begin{aligned}
    E\begin{pmatrix}
        x\\y\\z
    \end{pmatrix}
    &\mapsto
    \begin{pmatrix}
        a\\b\\c
    \end{pmatrix}\\
    F\begin{pmatrix}
        a\\b\\c
    \end{pmatrix}
    &\mapsto
    \begin{pmatrix}
        x\\y\\z
    \end{pmatrix}
\end{aligned}
$$
We might be tempted to consider $F$ to be the inverse of $E$, $E^{-1}$, however we might want to wait a bit before making this assertion.

This system of equations is what we call **consistent**. That means that there is a **unique** solution for  every unique  $x$,$y$ and $z$.

### Infinite Solutions

Now one thing we had was a system of 3 equations with 3 variables. Let's spice things up and take the following system of equations:
$$
\begin{aligned}
    3x + 3y &= 18\\
    2x + y + z &= 9
\end{aligned}
$$
I implore you to pause and solve this on your own using the methods we discussed previously on your own for practice, however I'm going to quickly walk through it.
$$
\begin{aligned}
    {1\over3}(3x + 3y) &= 18/3\\
    2x + y + z &= 9\\
    \\
    x + y &= 6\\
    2x + y + z - 2(x+y) &= 9 - 12\\
    \\
    x+y&=6\\
    -(-y+z)&=-(-3)\\
    \\
    x +y - (y-z) &= 6 - 3\\
    y - z &= 3
\end{aligned}
\quad
\begin{aligned}
    \\E_1&\rightarrow E_1/3\\
    \\
    \\E_2&\rightarrow E_2-E_1\\
    \\
    \\E_2&\rightarrow-E_2\\
    \\
    \\E_1&\rightarrow E_1-E_2\\
    \\
\end{aligned}
$$
And we are left with this irreducible system of equations:
$$
\begin{aligned}
    x + z &= 3\\
    y - z &= 3
\end{aligned}
$$
Now it might seem like we have done something wrong in the solving process, however I assure you that we have solved our sytem. The issue is that we were looking for a particular solution, however there is actually an *infinite* amount of solutions to this system. We can demonstrate this by setting $z$ to be a parameter $t$. This will give us a solved system that varies based on $t$.
$$
\begin{aligned}
    x &= 3 - t\\
    y &= 3 + t\\
    z &= t
\end{aligned}
\qquad\forall t\in\mathbb{R}
$$
Now we're going to run through a quick check to see if this is actually true:
$$
\begin{aligned}
    3(3-t) + 3(3+t) &= 9 + 9 + 3t-3t = 18\\
    2(3-t) + (3+t) + t &= 6 + 3 + 2t-2t = 9
\end{aligned}
$$
So as we can see our $t$ terms will always vanish so this will hold true for all $t$.

Now let's put these together. Remember that we're also going to have to include our $z$ here.
$$
\begin{aligned}
    x+z &= -{1\over3}E_1 + E_2\\
    y-z &= {2\over3}E_1 - E_2
\end{aligned}
$$
What happens if we plug in our original numbers 18 and 9?
$$
\begin{aligned}
    x+z &= -{1\over3}18 + 9 &= 3\\
    y-z &= {2\over3}18 - 9 &= 3
\end{aligned}
$$
As expected.

Let's try two new numbers 27 and 12
$$
\begin{aligned}
    x+z &= -{1\over3}27 + 12 &= 3\\
    y-z &= {2\over3}27 - 12 &= 6
\end{aligned}
$$
Giving this parameterized system:
$$
\begin{aligned}
    x &= 3-t\\
    y &= 6+t\\
    z &= t
\end{aligned}
\qquad\forall t\in\mathbb{R}
$$
So even though we've *kind of* found some inverse equations, there's still this weird parameterization that's sitting around. In this next section we will try to peer a little deeper in to that.

let's set our equations to be the same value of $E_1=E_2=0$
$$
\begin{aligned}
    x+z &= -{1\over3}0 + 0 &= 0\\
    y-z &= {2\over3}0 - 0 &= 0
\end{aligned}
$$
This leaves us with this parameterized system:
$$
\begin{aligned}
    x &= -t\\
    y &= t\\
    z &= t
\end{aligned}
$$
so anytime we have this case we're $z=y=-x$ our linear equations **all** collapse to the same value. In essence disappearing. We have an entire subset of combinations of $x$, $y$, and $z$ that simply go to nothing. This is called the **null set** for this system. However we will come back to explore this topic in greater detail at a later time.

So if we have a unique $x_1$ and $y_1$ and add a $y_2$, $x_2$, and include $z$ such that $z = y_2 = - x_2$ then we could almost imagine our system of linear equations as a linear function:
$$
E(x_1+x_2,y_1+y_2,z) = E(x_1,y_1,0) + E(x_2,y_2,z) = E(x_1,y_1,0) + 0
$$
When we think of linear equations like this, these random parameters in our solution seem to make a little more sense now. The parameters tell us the specific relationship that a particular $x_2$, $y_2$ and $z$ need to have to dissapear. They also tell us how we could construct any number that will always satisfy the equation we're looking for.

This type of system of equations is called **inconsistent**. Because there are multiple $x,y,z$ that lead to the same solution.

### No Solutions

Let's try one more example:
$$
\begin{aligned}
    3x+2y+1z&=13\\
    x+2y+3z&=10\\
    4x+4y+4z&=15
\end{aligned}
$$
Go ahead and try doing solving this, however you should end up with this relatively quickly.
$$
\begin{aligned}
    3z+2y+1x&=13\\
    x+2y+3z&=10\\
    0x+0y+0z&=-1
\end{aligned}
$$
But that's impossible, there seems to be a contradiction here. Because of this contradiction, we can only conclude that this system has **no solutions**. This system is also called **inconsistent** then as it is impossible to determine which $x,y,z$ led to a given solution.

### Inverse

From what we've just discovered, only **consistent** systems of linear equations can have this property were we can properly go backwards. So essentially, only consistent systems have inverse systems.

## Consistency of Linear Systems

As we have seen, only consistent systems have unique solutions. Whereas inconsistent do not. So this begs the question, is there a way to know when a system of linear equations is consistent without having to solve it?

### Determining Consistency

One thing we can notice immediately is that if there is a difference between the number of variables and the number of equations, then the system is already inconsistent. This makes sense because if we have, say, 3 variables, we will need 3 equations to represent each of their values. However if we only have 2 equations then we will only be able to properly elimante for 2 of the variables. The final one will become our parameter. The same goes for systems where there might be more equations than variables.

Let's think about a simple system of 2 equations in 2 variables:
$$
\begin{aligned}
    ax+by &= e\\
    cx+dy &= f
\end{aligned}
$$
One thing that becomes apparent is that if all our variables are zero then the system is inconsistent. However another observation along those lines shows that if $c=ka$ and $d=kb$ for some constant $k$, then our system is inconsistent, since the second equation is just the first one scaled by some factor. Once we begin our elimination we will be left with one equation and two variables. Addtionally our system will have no solutions if $f-ke\ne0$
$$
\begin{aligned}
    ax+by &= e\\
    cx+dy &= f
\end{aligned}
\quad
{\huge\rightarrow}
\quad
\begin{aligned}
    ax+by &= e\\
    kax+kby -k(ax+by)&= f-ke
\end{aligned}
\quad
{\huge\rightarrow}
\quad
\begin{aligned}
    ax+by&=e\\
    0x+0y &= f-ke
\end{aligned}
$$
There is nothing special about the ordering here, we could have also said $a=kc$ and $b=kd$.

Now let's think about what we would want to do if we were solving this system.
$$
\begin{aligned}
    ax+by &= e\\
    cx+dy &= f
\end{aligned}
\quad{\huge\rightarrow}\quad
\begin{aligned}
    ax+by&=e\\
    (ac-ca)x+(ad-bc)y&=f-ce
\end{aligned}
$$
Now if you notice, we do not want our system to look like:
$$
\begin{aligned}
    ax+by&=e\\
    0x+0y&=f-ce
\end{aligned}
$$
Since $ca-ac=0$, we need to make sure that $ad-bc$ does not equal zero either.

So in order to find out if our 2 variable 2 equation system is consistent, we only really need to check if $ad-bc\ne0$. We don't need to check if $f-ce\ne0$ since whatever that value is shouldn't matter so long as the $y$ variable has a non-zero coefficient. One thing you might notice, is that for a 2x2 system, we subtract the product of each corner. top left times bottom right minus top left times bottom right.

Let's try this again for a system of 3 equations and 3 variables:

$$
\begin{aligned}
    ax+by+cz&=j\\
    dx+ey+fz&=k\\
    gx+hy+iz&=l
\end{aligned}
$$

$$
\begin{aligned}
    ax+by+cz&=j\\
    0x+(ae-db)y+(af-dc)z&=k\\
    0x+(ah-gb)y+(ai-gc)z&=l
\end{aligned}
$$
So we need to make sure that these equations are consistent, notice that the bottom two lines are a system of linear 2 equations and 2 variables, which we already know how to check if it's consistent.
$$
(ae-db)(ai-gc)-(af-dc)(ah-gb)\ne0
$$
Substituting our terms we get:
$$

$$
So our full equation that we need to check is:

### Determinants

This is what is called the determinant of a matrix (for those of you already familiar with matrices). It is a way in which we can determine whether or not a system is consistent.

The determinant will also come in handy later when we start talking about matrices.


## Matrix Notation

So those of you who have already started a first course in linear algebra, or have been exposed to a bit of matrix notation already are probably wondering where they are.

I've decided to hold on to using matrices until I've already shown the process of solving linear systems. Since that is all that a matrix really is, it is just a way to represent a system of linear equations.

For example:
$$
\begin{aligned}
    ax+by+cz\\
    dx+ey+fz\\
    gx+hy+iz
\end{aligned}
$$
as the matrix:
$$
\begin{bmatrix}
a&b&c\\
d&e&f\\
g&h&i
\end{bmatrix}
$$
Essentially what I hope to achieve is show how linear algebra works on linear equations, and then move in to showing how talking about matrices helps us have a concrete representation of these systems and how we can manipulate them. As well as how those systems can act on arbitrary inputs, which will be our vectors. Or how vector spaces can represent all the combinations of inputs and outputs that are allowed.

So the next part of this series will be on Vector Spaces and how linear equations are actually representing operations over a vector space.

After that we will finally move on to more Matrix Theory and how to manipulate matrices, and what each manipulation means in the context of linear equations.
