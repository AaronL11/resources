\newpage

# Data Primitives

Okay so now it's time to start talking about how different programming languages handle different data.

## Working with Binary Data

We can usually create a binary number in our programming languages by typing the number out and putting a *b* at the end like so `10101011b`. Sometimes the `b` may be in front or behind but it's pretty similar across languages.

We can represent hexadecimal data and octal data the same way by doing `o` for octal and `x` or `0x` at the start for hex. Like binary, the location might be different across languages but it always uses the same characters.

### Bit Operations

The common logical operations, as well as the symbols used to describe them are:
1. NOT (`!`)
2. AND (`&`)
3. OR (`|`)
5. XOR (`^`)
6. NAND
7. NOR
8. XNOR

We can describe the last three in terms of the first four.

These are the truth tables for the various logic operations:
$$
\begin{aligned}
    &\begin{bmatrix}
        A&\big|&\text{NOT}\\
        \hline
        1&\big|&0\\
        0&\big|&1
    \end{bmatrix}\\
    \begin{bmatrix}
        A&B&\big|&\text{AND}\\
        \hline
        1&1&\big|&1\\
        1&0&\big|&0\\
        0&1&\big|&0\\
        0&0&\big|&0
    \end{bmatrix}
    &\begin{bmatrix}
        A&B&\big|&\text{OR}\\
        \hline
        1&1&\big|&1\\
        1&0&\big|&1\\
        0&1&\big|&1\\
        0&0&\big|&0
    \end{bmatrix}
    \begin{bmatrix}
        A&B&\big|&\text{XOR}\\
        \hline
        1&1&\big|&0\\
        1&0&\big|&1\\
        0&1&\big|&1\\
        0&0&\big|&0
    \end{bmatrix}\\
    \begin{bmatrix}
        A&B&\big|&\text{NAND}\\
        \hline
        1&1&\big|&0\\
        1&0&\big|&1\\
        0&1&\big|&1\\
        0&0&\big|&1
    \end{bmatrix}
    &\begin{bmatrix}
        A&B&\big|&\text{NOR}\\
        \hline
        1&1&\big|&0\\
        1&0&\big|&0\\
        0&1&\big|&0\\
        0&0&\big|&1
    \end{bmatrix}
    \begin{bmatrix}
        A&B&\big|&\text{XNOR}\\
        \hline
        1&1&\big|&1\\
        1&0&\big|&0\\
        0&1&\big|&0\\
        0&0&\big|&1
    \end{bmatrix}
\end{aligned}
$$

When we apply a logical operation between two binary numbers we simply apply that operation between every individual *bit*, or power of two. For example:

This is an example in C
```c
1010101b & 0101010b;
010101b ^ 111111b;
```
Here is an example in python:
```py
0b1010101 & 0b1000111
0b1010 ^ 0b0101
```

### Bit Masks

### One's Complement

### Two's Complement


## Boolean

Boolean's are a date type that represents either `true` or `false`. In some languages, like JavaScript, a boolean can actually evaluate to more values.

Booleans

Most programming languages will have some `assert` keyword or functionality built into them. This will stop the program if whatever expression it is evaluating is `false`, and continue if it is `true`.

C
```c
#include <assert.h>

assert(true);
```

Java
```java
assert true;
```

Rust
```rust
assert!(true);
```

Python
```py
assert True
```

### Boolean Operations

The boolean operations have the following structure:
```
expression1 [operation] expression2
```
They will perform some logical operation on these expressions.

The exception to this is the NOT operator which acts on one expression like so:
```
[NOT] expression
```

Here are all the boolean operations explained.

1. NOT `!`
   * swaps the truth value of the expression. `true` becomes `false`, `false` becomes `true`.
   * ```java
     assert !false;
     ```
2. AND `&&`
   * Checks if both expressions evaluate to `true`, returning `true` if so, otherwise `false.
   * ```py
     assert True && True
     ```
3. OR `||`
   * Checks if either expression evaluates to `true`, return `true` if so, otherwise `false`.
   * ```java
     assert true || false;
     ```
4. EQUAL `==`
   * checks if both expressions evaluate to the same truth value, if yes then it returns `true`.
   * ```rust
     assert!(true == true);
     ```
5. NOT EQUAL `!=`
   * checks if they are not equal and returns `true` if so, otherwise `false`.
   * ```py
     assert False != True
     ```

We can also nest expressions we are evaluating using brackets:
```c
#include <assert.h>

assert(true != (true && ~(true != false)));
```

## Numbers

### Integers

Integers are essentially just regular numbers that we are used to. These numbers are stored in binary which means that the highest number we can store depends on how large we want our binary number to be. Which means the more bits in we have the larger our number can be.

A 32-bit integer is an integer that has 32 bits, which is a much larger binary number than something like an 8-bit integer or 16-bit integer. It is most common to see 64-bit integers for most programs though. Most languages can work with up to 128 bit integers which can hold **a lot** of data, but require a lot more storage.

Here is an example of a 32-bit integer stored in binary:
$$
120~746_{10} = 011101011110101010_2
$$
Here is an 8-bit integer:
$$
170_{10} = 10101010_2
$$

### Signed Integers



## Floating Point

### Float 32

We have a single bit for the sign, and then 8-bits for the exponent. We then have an additional 23-bits for the mantissa.
$$
\color{green}{0}~\color{red}{10101010}~\color{blue}{10010101010100101000110}
$$
This represents the number given by equation
$$
{\color{green}\pm}(1+{\color{blue}mantissa})\cdot2^{{\color{red}exp}-127}
$$

### Float 64

### Double

### Number Operations

For the most part the basic mathematical operations can be done in all programming languages using the same symbols that we use in regular arithmetic.

1. Negation (`-`)
   * We can negate a number to make it negative by putting a minus sign in front of it
   * `-103`
2. Addition (`+`)
   * We can add two numbers by putting a plus between them
   * `1+2`
3. Subtraction (`-`)
   * We can subtract two numbers by putting a minus sign between them
   * `4-6`
4. Multiplication (`*`)
   * Multiplying happens when we put an asterisk between two numbers
   * `3*12`
5. Division (`/`)
   * This Operation divides to the nearest full integer if we divide two integer numbers.
     * Writing something like `12/6` will give us `2`, however writing `15/4` will also give us `2`
   * If however we divided two floating point numbers the result would be a floating point number.
     * `2.0/2.0` should give us `0.6666666666`
     * This also works for doubles.
   * In some languages the specifics might change depending on whether or not it's a type language.
6. Modulus (`%`)
   * This operation returns the remainder of two numbers
     * Writing something like `3%5` will give us `2` because 2 is the remainder when we divide 3 by 5

There are a few other symbols that are sometimes used, however not all languages implement them:

1. Matrix Multiplication (`@`)
2. Exponentiation (`**`)

Python uses both of these.

Usually any other mathematical operation will be done through some other means, like `pow(x,2)` for powers or `sqrt(x)` for square roots. Often languages will allow you to type something like `Math.<some operation>(x,...)`, for example `Math.add(x,y)` to perform `x+y`.

We'll get into how and why this happens later but just know that for the most part, arithmetic operations have the same syntax across languages.

We can get creative and creating interesting nested expressions with brackets:
```rust
(2/3 + (2-3)%2) + (10)*(-2*(4/3))
```

### Number to Boolean Operations

There are also operations we can do on numbers that will return booleans. These are our traditional comparison operations that we already are used to:

1. Greater Than (`>`)
   * returns `true` if the number on the left is strictly greater than the number on the right, `false` if they are the same or if the left is smaller.
   * ```java
     assert 5>2;
     assert !(5>5);
     ```
2. Less Than (`<`)
   * returns `true` if the left number is strictly less than the  rightmost number. If they are the same or if the left is greater, returns `false`.
   * ```rust
     assert!(2<5);
     assert!( !(2<2) );
     ```
3. Is Equal To (`==`)
   * returns `true` if the two numbers are the same, otherwise `false`
   * ```java
     assert 2==2;
     assert !(3==4);
     ```
4. Does Not Equal (`!=`)
   * returns `true` if they are not equal, `false` otherwise.
5. Greater Than or Equal To (`>=`)
   * return `true` if the leftmost number is greater than the right most number.
   * ```py
     assert 4>=3
     assert 3>=3
     ```
6. Less Than or Equal To (`<=`)
   * returns `true` if the number on the left is less than the number on the right, will also return `true` if the numbers are the same. Otherwise returns `false`.
   * ```py
     assert 2 <= 2
     assert 2 <= 3
     ```

We can combine these to make some more interesting expressions.

```c
#include <assert.h>

assert(false != (true && (100 > 3)));
```

In ducktyped languages like python and JavaScript we can also turn booleans into integers which allows us to perform some crazy combinations.

```py
2 + 3*((4<100)+2) - 10**(1==2)
```
in python and JavaScript this evaluates to `6`. **:D** But in C it's a syntax error


## Characters

### Ascii and Chars

### Unicode and Strings

## Pointers

## Special

### Null
