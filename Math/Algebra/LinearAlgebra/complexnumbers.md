\newpage

# Complex Numbers

## Motivations

$$
i^2 = -1
$$

## Complex Number Properties

Complex numbers have a variety of additional special properties that real number do not.

### Complex Conjugate

The complex conjugate of a complex number denoted $\overline{z}$ or $z^*$ simply reverses the sign on the imaginary part of the number.
$$
\overline{a+bi} \rightarrow a-bi
$$

### Modulus

If you look at a com

This length is called it's modulus, and it's given by the pythagorean theorem:
$$
|z| = \sqrt{a^2 + b^2}
$$
However if we inspect the radican we find that we can describe this in terms of multiplication with $z$'s conjugate:
$$
a^2+b^2 = (a+bi)(a-bi) = zz^*
$$
so in fact we can write the modulus in terms of $z$ and it's conjugate:
$$
|z| = \sqrt{zz^*}
$$

### Argument

The argument of a complex number is simply the angle it forms with the real number line in the complex plane.

We can rewrite a complex number in terms of it's modulus and argument by considering the associated $x$ and $y$ for $z$ as $|z|\cos\phi$ and $|z|\sin\phi$ respectively:
$$
z = |z|\big(\cos\phi+i\sin\phi\big)
$$

## Proving that $\mathbb{C}$ forms a field

### Addition

Adding two complex numbers happens component wise like this:
$$
(a+ib) + (c+id) = (a+b)+(d+b)i
$$
Since this addition is component wise we know that addition is commutative since it's analogous to addition over the real numbers.

Since the result is also complex number we know this is closed under addition.

### Additive Identity

Since addition is component wise, and those components are real numbers, we can basically just set our additive identity as having components made up of the additive identity in the real numbers, or 0:
$$
0+0i + a+bi = (a+0)+(b+0)i = a+bi
$$

### Subtraction and Negation

Just 
$$
(a+ib) - (c+id) = (a-b)+(d-b)i
$$
In fact this could also be described as adding the negative of $c+di$. We can also write addition and subtraction together like:
$$
(a+bi) \pm (c+di) = (a\pm b)+(d\pm b)i
$$

### Multiplication

Since complex numbers are composed of real numbers, we know that multiplication with a real number will be distributive like so:
$$
3(a+bi) = (3a)+(3b)i
$$
likewise if we attempt to multiply two complex numbers by distributing $a$ and $bi$ we notice we also get a complex number
$$
(a+bi)(c+di) = (ac-bd)+(ad+cd)i
$$
Thus $\mathbb{C}$ is closed under multiplication.

It's also commutative:
$$
(c+di)(a+bi) = (ca-db) + (ad+cd)i
$$
*We know this commutes because the multiplication on the real numbers commute*

### Multiplicative Identity

This one is pretty easy, we know from the real numbers that one is the multiplicative identity. Since complex numbers are composed of real numbers any multiplicative identity on $\mathbb{C}$ would have to also work on $\mathbb{R}$ so one will work here as well.
$$
1(a+bi) = (1)a+(1)bi
$$

### Division

Right away we can define complex division of $z$ with itself as:
$$
{a+bi\over a+bi} = 1
$$
From this we write a general divisor as:
$$
{1\over c+di} = {1\over c+di}{c-di\over c-di} = {c-di\over c^2+d^2}
$$
or in a more condensed form:
$$
{1\over z} = {z^*\over|z|^2}
$$
Division between two complex numbers $z$ and $w$ becomes:
$$
{z\over w} = {zw^*\over|w|^2}
$$
Which will give a complex number as $\mathbb{C}$ is closed under complex multiplication.

## The Meaning of Complex Multiplication

### 2D rotation

## Cartesian and Polar Form

$$
z = |z|(\cos\phi+i\sin\phi)
$$

### De Moivre's Formula

$$
(\cos x + i\sin x)^n = \cos nx + i\sin nx
$$

### Euler's Formula

$$
e^{i\phi} = \cos\phi + i\sin\phi
$$

This means we can go back and represent our polar form as:
$$
z = |z|e^{i\phi}
$$
In fact it can be useful to remember that for arbitrary angles we always have multiplies of $2\pi$ that we can add or subtract that will give us the same angle.
$$
z = |z|e^{i(\phi\pm2k\pi)},\quad k\in\mathbb{Z}
$$

This is related to De Moivre's Formula like so:
$$
(\cos\phi+i\sin\phi)^n=\left(e^{i\phi}\right)^n = e^{in\phi} = \cos n\phi + i\sin n\phi
$$

$$
e^{i\pi}+1=0
$$

## Complex Exponentiation

Thanks to this formula, complex exponentiation *and even multiplication* can be described in a relatively simple way:
$$
z^n = |z|^ne^{in\phi}
$$
$$
zw = |z||w|e^{i(\phi+\varphi)}
$$

Euler's Formula acts as an isomorphism from $(\mathbb{C},+)$ to $(\mathbb{C}^*,\cdot)$.

### Complex Roots of Unity

Let's attempt to find the squre root of an arbitrary complex number $z$. This becomes simple when we represent it in polar form:
$$
\begin{aligned}
\sqrt{z} &= \sqrt{|z|e^{i\phi\pm2k\pi}}\\
&=\sqrt{|z|}e^{i{\phi\over2}\pm k\pi}
\end{aligned}
$$
However now we need to adjust $k$ so it belongs to $\{0,1\}$, which is $\mathbb{Z}_2$. This makes sense due to the periodic nature of $2\pi$ in angles, since adding even and odd values of $k$ is essentially the same as adding either $0\pi$ or $\pi$ respectively.

Since the values of $k$ tell us we are adding $\pi$ to our angle, it represent us flipping our angle by $180^\circ$. When $z$ is a real number, this basically corresponds to taking it's negative! So this confirms that there are two values for square roots of real numbers $\pm\sqrt{x}$.

Now if we try the $n$-th root we'll, end up with something similar:
$$
\sqrt[n]{z} = \sqrt[n]{z}e^{i{\phi\over n}\pm2{k\over n}\pi}
$$
where $k\in\mathbb{Z}_n$.

Now we have a total of $n$ distinct values for $\sqrt[n]{z}$, corresponding to all the possible $k$s. These are called the **roots of unity**.

## Relation to Linear Equations

Complex Numbers can be described also in the realm of linear equations, if we treat 1 and $i$ like variables:
$$
a(1) + bi~ \rightarrow ~ax + by
$$
In fact 1 and $i$ form a basis for $\mathbb{C}$ over $\mathbb{R}$, but in order for that to make sense we need to look at how we can abstract the notion of a linear equation. Enter **Vector Spaces**.
