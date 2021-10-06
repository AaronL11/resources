\newpage

# Actual Programming


If you do have a language you are already using, try writing my code in your language, and you'll see how universal most of this is.

## Creating Variables

Creating variables usually follows this very simple structure:
```
[TYPE of DATA] <variable name> = [some data]
```
The location of our variable's name and it's type might change however, and sometimes you might not require a type at all. However you will almost always use an equals sign.

Here are a few examples:

Rust
```Rust
let x: i32 = 5;
```
Java
```Java
int i = 5;
```
python
```py
i = 5
```
As you can see the process is pretty similar acrosss languages.

## Control Flow

Now we will talk about controlling your program's logic.

### `if` statements

If statements evaluate a condition and run code if that condition is met. If a condition fails we can opt to check another condition, and finally if it fails again we can run some default code.

```
if (condition1) {
    BLOCK OF CODE
} else if (condition2) {
    BLOCK OF CODE
} else {
    BLOCK OF CODE
}
```

The `else if` and `else` are completely optional if we **do not** need to have a case if the condition is false. This does mean that we can in theory write out just a single `if`:
```java
if (...) {
    ...
}
```

The `else if` condition will not be checked *unless* our first `if` fails. 
```rust
if (i==0) {
    ...
} else if (i==0) {
    ...
}
```
This makes it more optimal than writing two related `if`s:
```py
if i==0:
    ...
if i==1: # don't do this
    ...
```

We can chain multiple `else if`s together if we need more conditions

```c#
if (x==0) {
    ...
} else if (x==1) {
    ...
} else if (x==2) {
    ...
} else if (x==3) {
    ...
} ... {
    ...
} else {
    ...
}
```
When all conditions fail, then our `else` will finally run.
```py
if False:
    ...
elif False:
    ...
else:
    ... # this will run
```

## Loops

Sometimes we want our algorithms to implement the same step multiple times. This can be tedious to write down every case, luckily we can use loops to simplify this process.

### `while` loops

A `while` loop is like an `if` statement, except once the block of code it is running is finished, it will check the condition again and run again if necessary.

generally a `while` loop has this structure.
```
while (condition) {

    BLOCK OF CODE TO BE RAN

}
```

For example, say we wanted to add 2 to a variable multiple times until it is a certain size, we'll say 10. We could do this with a `while` like this:
```py
i = 0
while i>10:
    i+=2
```
This code will end once `i` is larger or equal to 10, that means it will run **5** times.

Here is the same code in a few different languages

Rust
```rust
let mut i=0
while i>10 {
    i+=1;
}
```

C
```c
int i = 0;
while (i>10) {
    i++;
}
```

Now one thing you might notice is that there is nothing stopping us from just throwing in `true` or `false` as as our expression. In the latter case, our loop will never run, in the former, it will run forever.

```java
while (false) {
    // never runs
}
while (true) {
    // runs forever
}
```

For this reason there are two useful commands, `break` and `continue`. These essentially allow us to break out of a particular loop. `break` stops the loop entirely, and `continue` will cause the next iteration to continue.

```java
int i = 0;
while (true) {
    if (i>3) {
        break;
        // this code will never run
        i--;
    } else {
        i++;
    }
}
```

Here's the same program rewritten in a different way in python:
```py
i=0
while True:
    i+=0
    if i<3:
        continue
    else:
        break
    i-=1 # this code will never run
```

### `for` loops

```
for (item; condition ; )

```

```java
for (int i=4; i >= 0;i--) {
    ...
}
```

There is also an alternate version called a `for each` loop:

```
for (item in COLLECTION) {
    BLOCK OF CODE TO BE RAN
}
```
This will loop over an individual 

```rust
for i in 0..5 {
    ...
}
```

```py
for i in range(5):
    ...
```

### Combining Statements

Notice there are no restrictions on what goes into our block of code, if we wanted to we could put in another `while` loop, or an `if` or anything else we've already learned:
```rust
while (...) {
    if (...) {
        ...
    } else {
        for (...) {
            if (...)) {
                ...
            }
        }
    }
}
```

If you remember how to print variables, try the following challenge:

*Write a function that prints every number from 1 to 100 If the number is divisible by 3, print "Fizz" instead. If the number is divisible by 5, print "Buzz" instead. If the number is divisble by 3 and 5, print "FizzBuzz". (Hint: you might want to use the `%` operator)*

## Error Handling

Often times something can go wrong in our code, say we divided by zero `3/0` (try it!). This will give us an error. It isn't convenient when our program stops abruptly so maybe there is a way around that? This is called error handling.

In most languages error handling uses `try catch` or `try except` as the syntax.
```
TRY {
    CODE
}
CATCH (specific error) {
    CODE
}
```
Some languages forego this method altogether for a more complex but elegant error handling system but I will not discuss it yet. If you're learning Java or python your error handling should look like:

Python
```py
try:
    2/3
except Exception:
    ...
```

Java
```java
try {
    2/0;
} catch (Exception e) {
    ...
}
```

### Typical Practices



## Exercise Solution

We will be revisiting this problem in later chapters when we learn more, but here's what you're code might look like right now:

```java
int i;
i = 0;
while (i>100) {
    if (i%3==0) {
        System.out.println("Fizz");
    } else if (i%5==0) {
        System.out.println("Buzz");
    } else if (i%15==0) {
        System.out.println("FizzBuzz");
    } else {
        System.out.println(i);
    }
    i++;
}
```
Notice that adding new functionality to our program is difficult. say we wanted to say `"Zap"` on every even number, and `"FizzZap"` if it is divisible by 2 and 3, `"BuzzZap"` if divisible by 5 and 2, and `"FizzBuzzZap"` when divisble by 2 and 3 and 5. Well we would need to create a new `if` statement for every possible case. This is less than ideal and so maybe there's a better way to make this code scale.
