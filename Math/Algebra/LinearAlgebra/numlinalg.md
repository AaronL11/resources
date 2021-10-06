\newpage

# Intro to Numerical Linear Algebra

Thanks to advances in modern technology we have been able to use computers to solve many of the matrix problems we face. However due to the way floating point numbers are stored it is impossible to accurately represent certain data. As we continously apply transformations the difference between the real data and the numerical approximations becomes larger and larger. Computer Linear Algebra Systems and Numerical Linear Algebra use a variety of techniques to minimize this error with an emphasis on efficiency.

Since numerical linear algebra is a subset of mathematics and computer science, this section will contain a lot of coding concepts, including many more intermediate to advanced coding concepts (your basically reading a tutorial on how to make numpy from scratch, this is **not** for beginners). So fair warning to the reader.

I will be writing examples in both Python and Rust.

## Matrix Optimizations

### Householder Transformation

$$
x - 2vv^\dagger x
$$
Which can be represented as the matrix multiplication $Px$ where $P$ is:
$$
P=I-2vv^\dagger
$$

### Givens Rotation

## Finding Eigenvalues

### Using Hessenberg Matrices

## Iterative Methods

### Arnoldi Iteration

## Matrix Decompositions

### LU

### QR

### SVD

### Eigendecompositions

## Solving Systems of Equations
