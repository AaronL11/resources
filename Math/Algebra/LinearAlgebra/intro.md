\newpage

# Introduction

## Motivating Example

Amber is looking to buy some apple cider, bread, and cookies from the store. However she has limited money in her wallet and limited space in her car. She only has room in her car for 4 L of groceries, and she can only spend 13 dollars. Additionally she can't carry more than 10 kg of groceries. Given that each bottle of cider cost $3, weighs 1 kg, and has a volume of 400 mL, each cookie costs $2, weighs 0.5 kg, with a volume of 240 mL, each piece of bread cost $5, has a volume of 1500 mL, and weighs 1 kg; how many groceries can she buy?

For those who know a little algebra, you might recognize that we can form a single equation for the cost of each of our groceries. Then we can write one for the volumes, and one for the weights.
$$
\begin{aligned}
    3a + 5b + 2c &= 13\\
    0.4a + 1.5b + 0.25c &= 4\\
    1a + 1b + 0.5c &= 10
\end{aligned}
$$
But how would we go about solving this?

This is called a system of linear equations, and they've been known to humans for millenium. In fact the chinese wrote about how to solve systems like this in *The Nine Chapters of the Mathematical Art* written as far back as 200 BC.

What I hope to tackle in these upcoming videos is finding new ways to look at and understand linear equations and how to solve them. Later advancing to new notations and a deeper look into the extension of these ideas through the tools of **Linear Algebra**.

This is meant to be similar to 3B1B's linear algebra playlist. Except rather than solely teaching intuition I will be going through the mechanics and inner workings of matrices and vectors, discussing the algorithms and tools that we us to solve these. Hopefully through the lens of linear equations with various examples and explanations along the way. I'm hoping to cover as much ground as possible while also building a stronger and stronger understanding of these systems.

Most linear algebra courses will usually begin with linear equations and then quickly jump in to matrices. I am going to be doing something slightly different were I will save matrices till later. This is because matrices will make more sense when we have a stronger grasp of linear equations and the vector spaces that form them.

The structure of these videos will be as follows:

1. Linear Equations
   * We will begin discussing linear equations and develop a few tools and understanding surrounding them.
2. Vector Spaces
   * We will then move on to take a deeper look at vectors and their relation to general systems of equations.
3. Matrices
   * We will then look at matrices and how they relate to linear equations and vector spaces. 
4. Additional Components
   * At this point we will discuss additional topics in linear algebra as well as some applications.

## Outcomes

The outcomes of this booklet and series of videos are:

1. Strong Intuition for the fundamentals
   1. Connection between linear equations and determinants, matrices and vectors
   2. Understanding when to represent a problem as a linear system and solve with matrices
2. Understand a brief history of Linear Algebra and some of the work that's been done
   1. Pre-European history and Chinese origins
   2. European formulations
   3. Mathematicians and Important Time Periods
3. Understanding of the connections between Linear Algebra and other parts of mathematics
   1. Abstract Vector Spaces
   2. Linear Transformations
   3. Quadratic Forms
4. Identify **why** something works
   1. Why is RREF important/useful
   2. Where do determinants come from
   3. Why does the Gram-Schmidt Algorithm work/exist
   4. Why does the SVD exist
   5. Why can we represent a certain problem as a matrix operation
5. As well as a variety of advanced techniques
   1. Hilbert Spaces
   2. Algorithm Optimizations
      1. Linear-Least Squares (QR Decomposition)
      3. Computational Methods for Matrix solving
   3. Advanced Matrix Operations
      1. Kronecker
      2. Direct Sum
   4. Advanced Vector Space Operations
      1. Outer Product
      2. Wedge Product
   5. Basic Tensor Theory

## History

\newpage