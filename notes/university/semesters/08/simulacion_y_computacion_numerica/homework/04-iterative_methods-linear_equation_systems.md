
# Iterative methods for solving linear equation systems

## No computer problems

### 1

The following system of equations is designed to determine concentrations (the $c$ values are in $\frac{ \text{g} }{ \text{m}^3 }$) in a series of coupled reactors as a function of the input mass quantity to each of them (the right sides are in $\frac{ \text{g} }{ \text{d} }$),

$$
\being{array}{cccc}
    & 15 c_1 & - 3 c_2  & - c_3   & = 3,800 \\
    & -3c_1  & + 18 c_2 & - 6c_3  & = 1200 \\
    & -4c_1  & - c_2    & + 12c_3 & = 2350
\end{array}
$$

Solve this problem using the Gauss-Seidel method with $\varepsilon_s = 5\%$.

### 2

Solve the first problem using Jacobi's method.

### 3

Use the Gauss-Seidel method without relaxation, and with relaxation ($\lambda = 1.2$), to solve the following system for a tolerance of $\varepsilon_s = 5\%$.

> If necessary, rearrange the equations to achieve convergence.

$$
\being{array}{cccc}
    & 2 x_1  & - 6 x_2 & - x_3   & = -38 \\
    & -3 x_1 & - x_2   & + 7 x_3 & = -34 \\
    & -8 x_1 & + x_2   & - 2 x_3 & = -20
\end{array}
$$

### 4

Solve the third problem using Richardson's method.

### 5

From the following three sets of linear equations, identify which one(s) cannot be solved using an iterative method like Gauss-Seidel. Demonstrate that the solution does not converge, using any number of iterations as needed. Clearly state your convergence criterion (i.e., how you know it is not converging).

1. Set one.

    $$
    \begin{array}{cccc}
        & 9 x_1  & + 3 x_2 & + x_3   & = 13 \\
        & -6 x_1 &         & + 8 x_3 & = 2 \\
        & 2 x_1  & + 5 x_2 & - 1 x_3 & = 6
    \end{array}
    $$

2. Set two.

    $$
    \begin{array}{cccc}
        & x_1   & + x_2   & + 6 x_3  & = 8 \\
        & x_1   & + 5 x_2 & - 1 x_3 & = 5 \\
        & 4 x_1 & + 2 x_2 & - 2 x_3 & = 4
    \end{array}
    $$

3. Set three.

    $$
    \begin{array}{cccc}
        & -3 x_1 & + 4 x_2 & + 5 x_3 & = 6 \\
        & -2 x_1 & + 2 x_2 & - 3 x_3 & = -3 \\
        & 2 x_1  & + 0 x_2 & - 1 x_3 & = 1
    \end{array}
    $$

## Computer problems

Program the Gauss-Seidel method and test it on these examples:

### a

$$
\begin{cases}
    & 3 x & + y  & + z  & = 5 \\
    & x   & + 3y & - z  & = 3 \\
    & 3 x & + y  & - 5 z & = -1 \\
\end{cases}
$$

### b

$$
\begin{cases}
    & 3 x & + y   & + z   & = 5 \\
    & 3 x & + y   & - 5 z & = -1 \\
    & x   & + 3 y & - z   & = 3 \\
\end{cases}
$$

Analyze what happens when these systems are solved using simple Gaussian elimination without pivoting.
