\newpage

# Common Data Types

## Array

Arrays are a **mutable** **ordered** data type. Which means they have a clear ordering and you can edit what's inside.

An array is a contigious sequence in memory that contains items of a single type. It's size cannot be altered once created. You can index into an array and peek inside by writing square brackets next to the array and writing an index. You can also use the `=` operator if you've selected an element from an array to change it.
```
ARRAY[Type; Size] name = [item, item, item, ..,];

Type var = array[index];

array[index] = <variable that has right type>;
```
**IMPORTANT:**\
Arrays are **zero indexed**, which means that to get the first element you need to do `Array[0]`. This is because an array is simply a pointer to a contigious sequence in memory, and the index is just offsetting that pointer. So an offset of `0` is the first element in the array, and an offset of `1` would be the second. So if an array has `n` elements, you would index it with numbers `0` to `n-1`. Indexing an array with a number greater than it's size is an error though.

Here is an example in two languages:
```java
int[5] intArray = {1,2,3,4,5};
assert 4 == intArray[3];
intArray[1] = 4 // the array is now {1,5,3,4,5}
```

```rust
let mut array: [u32;5] = [1,2,3,4,5];
let x: u32 = array[3];
```

We can also create double nested arrays and more:
```java
int[3][3] intMatrix = {{0,1,2},{3,4,5},{6,7,8}};
```

An array also has access to it's size. We can grab an arrays size usually by typing `Array.size()` or `Array.len()`. It varies by language but you can find it.
```java
int[3] Array = {1,2,3};
assert Array.length == 3;
```

```py
x = [0,1,2]
assert len(x)==3
```

## Tuple

A tuple is like an array, it has a fixed length and can be indexed. Unlike an array however, the items inside a tuple cannot be changed. Tuples will usually use parenthesis to define them:
```
TUPLE[Type] name = (item, item, item)

Type var = tuple[index]
```

```py
(1,2,3)
```

Tuples are an **immutable** **ordered** data type.

## ArrayList

Like arrays, `ArrayList`s are **mutable ordered** data types.


```py
x = [1,2,3]
x.append(4)
assert x == [1,2,3,4]
x.pop()
assert x == [1,2,3]
```

```py
matrix = [
    [0,1,2],
    [3,4,5],
    [6,7,8]
]
```

## Hashmap

A hashmap is an **unordered mutable** data type

These are also called look up tables

## Set

A set is an **unordered immutable** data type.

## Enum

## Struct

```C
struct {

}
```

## Class



```java
public class MyClass {
    /*
     * Constructor
     */
    public MyClass() {
        ...
    }

    public void MyMethod() {
        ...
    }
}
```


```py
class MyClass:
    def __init__(self):
        ...
```
