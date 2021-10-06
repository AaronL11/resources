hmm, I think there are some symmetries we can take advantage of to optimize the problem.
I went ahead and took a look at $n=4$. I took to writing out a tree of all permutations, but that quickly got annoying and I noticed that some orders of flips will lead to the same results.
$$
\begin{aligned}
T(1,2,3,4) = (4,3,2,1)\quad F(1,2,3,4) &= (1,3,2,4)\quad G(1,2,3,4) = (4,3,2,1)\\
G = T\circ F &= F \circ T
\end{aligned}
$$
So we can think of this as transformations on our original list `[1,2,3,4]`.

Now we can represent these permutations as the matrix transformation:
$$
\begin{bmatrix}
1&0&0&0\\
0&0&1&0\\
0&1&0&0\\
0&0&0&1
\end{bmatrix}
\begin{bmatrix}
1\\2\\3\\4
\end{bmatrix}
=
\begin{bmatrix}
1\\3\\2\\4
\end{bmatrix}
$$

Now we know that 4! = 24, but in fact there are actually less transformations necessary to describe all the permutations.
These are all the matrices we can form for the transformations:
$$
\begin{aligned}
\begin{bmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&1&0\\
0&0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
0&1&0&0\\
1&0&0&0\\
0&0&1&0\\
0&0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
0&0&1&0\\
0&1&0&0\\
1&0&0&0\\
0&0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
0&0&0&1\\
0&1&0&0\\
0&0&1&0\\
1&0&0&0
\end{bmatrix}
\\
\begin{bmatrix}
1&0&0&0\\
0&0&1&0\\
0&1&0&0\\
0&0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
1&0&0&0\\
0&0&0&1\\
0&0&1&0\\
0&1&0&0
\end{bmatrix}
\quad
\begin{bmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&0&1\\
0&0&1&0
\end{bmatrix}
\end{aligned}
$$
These **7** transformations form a group under matrix multiplication and any possible permutations of (1,2,3,4) is the result of the composition of these 7 transformations.

Now let's do the same for 3x3:
$$
\begin{aligned}
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
0&1&0\\
1&0&0\\
0&0&1
\end{bmatrix}
\\
\begin{bmatrix}
0&0&1\\
0&1&0\\
1&0&0
\end{bmatrix}
\quad
\begin{bmatrix}
1&0&0\\
0&0&1\\
0&1&0
\end{bmatrix}
\end{aligned}
$$

Now if you notice, all of these transformations are essentially subtransformations in our n=4 transformation Group.

We can represent this as the direct sum of our matrices:
$$
A\oplus B =
\begin{bmatrix}
A&0\\
0&B
\end{bmatrix}
$$
So for example:
$$
[1]\oplus
\begin{bmatrix}
0&1&0\\
1&0&0\\
0&0&1
\end{bmatrix}
=
\begin{bmatrix}
1&0&0&0\\
0&0&1&0\\
0&1&0&0\\
0&0&0&1
\end{bmatrix}
$$
And for our n=3 group, we can also represent these as the direct some of n=1 and n=2 matrices, and n=2 as the direct sum of n=1 matrices.
Now this is where things get interesting because we can represent some matrices in our n=4 group as the direct sum of smaller matrices of n=1, n=2, and n=3.
So for example:
$$
\begin{bmatrix}
0&1&0&0\\
1&0&0&0\\
0&0&1&0\\
0&0&0&1
\end{bmatrix}
=
\begin{bmatrix}
0&1\\
1&0
\end{bmatrix}
\oplus
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix}
$$

So what we've done is found a way to describe the permutation transformations for n=4 in terms of n=3,2,1. Without loss of generality we could have essentially continued this for n=5 and in n=k.

Additionally, some of the transformations are *flipped* versions of each other:
$$
\begin{aligned}
\begin{bmatrix}
0&0&0&1\\
0&1&0&0\\
0&0&1&0\\
1&0&0&0
\end{bmatrix}
&=
\text{fliph}\left(
\begin{bmatrix}
1&0&0&0\\
0&0&1&0\\
0&1&0&0\\
0&0&0&1
\end{bmatrix}
\right)\\
&=\text{fliph}\left(
[1]
\oplus
\begin{bmatrix}
0&1\\
1&0
\end{bmatrix}
\oplus
[1]
\right)
\\
&=
\text{fliph}(
[1]\oplus
\text{fliph}([1]\oplus[1])
\oplus[1]
)
\end{aligned}
$$
Which is equivalent to multiplying by the matrix:
$$
\begin{bmatrix}
0&0&0&1\\
0&0&1&0\\
0&1&0&0\\
1&0&0&0
\end{bmatrix}
$$
There are also some vertical flips, but we can essentially write all the transformations in n=4 as the horizontal and vertical flipped direct sums of 4 n=1 transformations.

Now let's take a look at n=3 again:
$$
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1
\end{bmatrix}
\quad
\begin{bmatrix}
0&1&0\\
1&0&0\\
0&0&1
\end{bmatrix}
\\
\begin{bmatrix}
0&0&1\\
0&1&0\\
1&0&0
\end{bmatrix}
\quad
\begin{bmatrix}
1&0&0\\
0&0&1\\
0&1&0
\end{bmatrix}
$$
If you notice we only actually have 2 unique transformations and they're both flipped.

In fact we can reduce n=3 to just these transformations:
$$
\left\{
[1]\oplus[1]\oplus[1],
~[1]\oplus
H([1]\oplus[1])
\right\}
$$
I simplified the notation for vertical (V) and horizontal (H) flipping.

This group is acted on by the group of V and H under composition:
$$
\{e,V,H\}
$$
where e is our identity, so no flipping essentially.
Compositions of V and H acting on our groups will give us the other two transformations for n=3.

Now one thing to note here, let's take a quick look at n=2:
$$
\{[1]\oplus[1]\}
$$
All transformations on n=2 come from applying {e,V,H} on this set.
And if you look even closer you'll see that it's the direct sum of `[1]` on each element of the action of our flipping group on the group of transformations of n=2.

We can even do this for n=4:
$$
\begin{Bmatrix}
[1]\oplus[1]\oplus[1]\oplus[1],&
[1]\oplus H([1]\oplus[1]\oplus[1]),\\
[1]\oplus H([1]\oplus[1])\oplus[1],&
[1]\oplus[1]\oplus H([1]\oplus[1])
\end{Bmatrix}
$$
I'm going to simplify this notation to be:
$$
[1]\oplus
\begin{Bmatrix}
[1]\oplus[1]\oplus[1],\\
[1]\oplus H([1]\oplus[1])
\end{Bmatrix}
$$
Which is:
$$
[1]\oplus\LARGE\left\{[1]\oplus\huge\{[1]\oplus[1]\}\right\}
$$

We can basically construct the transformation group for n=k as the direct sum of `[1]` and the transformation group n=k-1:
$$
\text{Perms}(k) := 1\oplus\text{Perms}(k-1)
$$

Okay so I know this kind of got a bit abstract so let's look back at an example:
So remember, all permutations of n=3 look like:
```
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1
```
I'm going to abuse notation and just write these like this:
$$
1\oplus
\begin{aligned}
2\quad3\\
3\quad2
\end{aligned}
\quad
2\oplus
\begin{aligned}
1\quad3\\
3\quad1
\end{aligned}
\quad
3\oplus
\begin{aligned}
1\quad2\\
2\quad1
\end{aligned}
$$
and we can express the n=4 group as:
$$
1\oplus~\text{perms}(2,3,4)
\quad
2\oplus~\text{perms}1,3,4
\quad
3\oplus~\text{perms}1,2,4
\quad
4\oplus~\text{perms}1,2,3
$$
Notice how this is the direct sum of the value and all permutations with that value removed?

As you can see we've found a recursive way to express our transformations, and it's important to notice that this won't generate any dublicate values.

So now it's only a matter of figuring out how to code this. Well this is actually really simple.

We'll start by defining a permutation function
```py
def perm(l: list) -> list:
  ...
```
Then we set the base case for a list of length one and two:
```py
if len(l) == 1:
  return l
elif len(l)==2:
  return [l[0],l[1]], [l[1],l[0]]
```
For 2 numbers we really are just taking our numbers and then swapping them.

Now what we want to do next is make a function that will remove a value from a list, here's what I came up with:
```py
def remove(i,l):
  return [x for x in l if x!=i]
```
This function will be used to remove the specified value so we can add it to our list.

Now we have enough to cover n>2:
```py
else:
  return [[i]+p for i in l for p in perm(remove(i,l))]
```

So our full function looks like:
```py
def remove(i: int,l: list) -> list:
  return [x for x in l if x!=l]

def perm(l: list) -> list:
  if len(l) == 1:
    return l
  elif len(l)==2:
    return [l[0],l[1]], [l[1],l[0]]
  else:
    return [[i]+p for i in l for p in perm(remove(i,l))]
```

This will work for any list of values `[a,b,c]` too.


## Some additional things I've looked at:

If we analyze how we constructed our transformations we could have also noticed we could have constructed $n=4$ like so:
$$
\{\{[1]\oplus[1]\}\oplus\{[1]\oplus[1]\}\}
$$
The span of such forms a left module under flipping:
$$
a
\begin{Bmatrix}
    \begin{bmatrix}
        1
    \end{bmatrix}
    \oplus
    \begin{bmatrix}
        1
    \end{bmatrix}
\end{Bmatrix}
\oplus
b
\begin{Bmatrix}
    \begin{bmatrix}
        1
    \end{bmatrix}
    \oplus
    \begin{bmatrix}
        1
    \end{bmatrix}
\end{Bmatrix}
,\quad a,b\in\{e,V,H\}
$$

In fact we can write all even and odd numbers as the following spans in a left-module:
$$
n=2k \implies\left\{\bigoplus_i^nF_i\{[1]\oplus[1]\}\right\}\\
n=2k+1 \implies \left\{\bigoplus_i^{n-1}F_i\{[1]\oplus[1]\}\oplus[1]\right\}\\
$$
Where $F_i$ is the flipping coefficient.

This has the consequence that we can describe all permutations in terms of transformations on a much smaller basis.

For $n=3$ that basis looks like:
$$
1,2,3,12,23,31
$$
cause any permutation of $n$ numbers can be described as:
$$
a\oplus F(b),\quad a\in\{1,2,3\}~b\in\{12,23,31\}
$$
Where $H$ represents some flip, (either nothing or reversed).s


and $n=4$ has the basis:
$$
12,13,14,23,24,34
$$
and all permutations are comprised by:
$$
F(a)\oplus F(b),\quad a,b\in\{12,13,14,23,24,24\}
$$
