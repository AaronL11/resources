\newpage

# logic

## identity (=)

In logic the equals sign means that two statements are the same.
$$
P = Q
$$
So this is read $P$ **is** $Q$.

## negation ($\neg$)

The negation operator simply reverses a statement's truth value. Pronounced not. For example, if proposition $P$ is **true**, then $\neg P$ is **false**.

## possibly ($\lozenge$)

## necessarily ($\square$)

## logical equivalence ($\equiv$)

The logical equivalence operator indicates that two statements are the same conceptually.
$$
P \equiv Q
$$

## definition ($:=$)

## if then ($\rightarrow$)

This is one of the most basic logical statements, an *if then* statement basically has the form if $P$ is true, then $Q$ must be true also. The syntax is an arrow pointing from $P$ to $Q$.
$$
P \rightarrow Q
$$
Keep in mind that this isn't always true in reverse. There's what's called the converse conditional, essentially it's the same except you would say if $Q$ then $P$, and the syntax is a left arrow.
$$
P \leftarrow Q
$$

## implies ($\implies$)

## implied by ($\impliedby$)

## if and only if ($\iff$)

An if and only if statement, also called the biconditional, is a relationship between two statements where both the conditional and it's converse are true. In english this is like saying, if $P$ then $Q$, and if $Q$ then $P$.
$$
P \iff Q \equiv (P\rightarrow Q) \land (P\leftarrow Q)
$$
The syntax is a two sided arrow pointing to both statements.

## logically equivalent to ($:\iff$)

## tautology ($\top$)

Also called Verum, a tautology represents something that is always true.
$$
\top
$$
It is equivalent to the statement if $P$ then $P$ for all $P$:
$$
\top P \equiv \forall P(P\rightarrow P)
$$

## contradiction ($\bot$)

Also called Falsum, a contradiction is the opposite of a tautology.

## logical conjunction ($\land$)

The logical conjuction has the same semantic meaning as the english word *and*.
$$
P \land Q
$$
Means $P$ and $Q$

## logical or ($\lor$)

## xor ($\oplus$)

The XOR operator can be used as a closed addition operator over the boolean domain:
$$
\begin{aligned}
    0\oplus0 = 0 = 1\oplus1\\
    1\oplus0 = 1 = 0\oplus1\\
\end{aligned}
$$

## for all ($\forall$)

This quantifier states that what ever statement we make is true for every possible value that some variable can take. The syntax is an upside down capital A.

For example, let's write out the following statement:\
For all n where n is an even integer, n divided by 2 is an integer.
$$
n/2\in\mathbb{Z},~\forall n\in 2\mathbb{Z}
$$

## existence ($\exists$)

The existence quantifier, denoted by this backwards capital E, declares that the statements that follows is true for at least one value. There is a modified version that has an exclamation mark behind the E.

For example take the statement:\
There exists a single real number x such that x + y = y for all real numbers y.
$$
\exists!x\in\mathbb{R} : x+y = y,~\forall y\in\mathbb{R}
$$

## proves ($\vdash$)

## models ($\models$)


## Because ($\because$)



## Therefore ($\therefore$)




## Q.E.D. ($\blacksquare$)

An abbreviation of a lating phrase *Quod Erat Demonstratum*, meaning "which was to be demonstrated". It is a fancy notation to demonstrate the end of a mathematical proof, usually denoted by a black square at the bottom of a proof.# Algebra


