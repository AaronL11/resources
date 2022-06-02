\newpage

# Set Theory

## Set Builder Notation

Set builder notation is a common notation used for defining sets. In set builder notation you are defining a set to be a collection of elements where a given property is true:
$$
S = \{x~\text{such that}~x~\text{is even}\}
$$
This is an example set of even numbers.

## such that (| or :)

The $|$ and $:$ symbols are used in set builder notation to mean *such that* or *such as*. Returning to our previous example we can rewrite our set $S$ as:
$$
S = \{x:x~\text{is even}\} = \{x~|~x~\text{is even}\}
$$

## element of ($\in$)

This epsilon looking symbol is used to denote the fact that a certain symbol represents an element of some set. It is usually written as element$\in$set. For example,
$$
x\in\{0,1,2,3\}
$$
this means that $x$ can be either 0,1,2 or 3.

We can exclude a mathematical object by being in a set by doing the not in sign $\not\in$.

## contains ($\ni$)

This is the reverse of the set element sign and is used to indicate that a particular set has a specific object. For example,
$$
\{0,1,2,3\}\ni2
$$
This is read as: the set contains 2.

Like with the set element symbol, we can cross this one out to mean *does not contain* $\not\ni$
$$
\{0,1,2,3\}\not\ni4
$$

## subset of ($\subset$)

The subset symbol denotes a subset

$$
\{0,1\}\subset\{0,1,2,3\}
$$

## superset of ($\supset$)


$$
\mathbb{N}\supset\{0,1,2,3\}
$$

Just like with subsets, we put an underline if the two sets may be equal $\supseteq$


## complement ($\complement$)

The complement of a set is every element that is not in that set.
$$
A^\complement = \{x:x\not\in A\}
$$
For example:
$$
\{0,1,2,3\}^\complement = \{4,5,..,\infty\}
$$

Other notations look like

## union ($\cup$)

The union of two sets $A,B$ is a new set where any element is in $A$ or in $B$.
$$
A\cup B = \{x:x\in A \lor x\in B\}
$$

## intersection ($\cap$)

The intersection of two sets $A,B$ is every element in $A$ that is also in $B$.
$$
A\cap B = \{x:x\in A\land x\in B\}
$$
