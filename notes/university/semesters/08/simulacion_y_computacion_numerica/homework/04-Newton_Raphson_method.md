# Newton Raphson method

## 22

Starting with $(0,0,1)$, carry out an iteration of Newton's method for nonlinear systems on:

$$
\left \{ \begin{align*}
    x y - z^2         & = 1 \\
    x y z - x^2 + y^2 & = 2 \\
    e^x - e^y + z     & = 3
\end{align*} \right .
$$

$$
x = x_1 \quad y = x_2 \quad z = x_3
$$

$$
F = \left \{ \begin{align*}
    x_1 x_2 - { x_3 }^2 - 1                 & = 0 \\
    x_1 x_2 x_3 - { x_1 }^2 + { x_2 }^2 - 2 & = 0 \\
    e^{ x_1 } - e^{ x_2 } + x_3 - 3         & = 0
\end{align*} \right . \\[10 pt]

\begin{bmatrix}
    x_1 x_2 - { x_3 }^2 - 1 \\
    x_1 x_2 x_3 - { x_1 }^2 + { x_2 }^2 - 2 \\
    e^{ x_1 } - e^{ x_2 } + x_3 - 3
\end{bmatrix}
=
\begin{bmatrix}
    0 \\
    0 \\
    0
\end{bmatrix}
$$

$$
J = \begin{bmatrix}
    x_2             & x_1             & -2 x_3 \\
    x_2 x_3 - 2 x_1 & x_1 x_3 + 2 x_2 & x_1 x_2 \\
    e^{ x_1 }       & -e^{ x_2 }      & 1
\end{bmatrix}
$$

Replacing the starting point in $F$.

$$
x_1 = 0 \quad x_2 = 0 \quad x_3 = 1
$$

$$
F(0,0,1) = \begin{bmatrix}
    x_1 x_2 - { x_3 }^2 - 1 \\
    x_1 x_2 x_3 - { x_1 }^2 + { x_2 }^2 - 2 \\
    e^{ x_1 } - e^{ x_2 } + x_3 - 3
\end{bmatrix}
=
\begin{bmatrix}
    -2 \\
    -2 \\
    -2
\end{bmatrix}
$$

Replacing the starting point in $J$.

$$
J(0,0,1) = \begin{bmatrix}
    0 & 0  & -2 \\
    0 & 0  & 0 \\
    1 & -1 & 1
\end{bmatrix}
$$

The final equation is:

$$
\begin{bmatrix}
    0 & 0  & -2 \\
    0 & 0  & 0 \\
    1 & -1 & 1
\end{bmatrix}
\begin{bmatrix}
    h_1 \\
    h_2 \\
    h_3
\end{bmatrix}
=
- \begin{bmatrix}
    -2 \\
    -2 \\
    -2
\end{bmatrix}
=
\begin{bmatrix}
    2 \\
    2 \\
    2
\end{bmatrix}
$$

The resulting equation system is

$$
\left [ \begin{array}{rrr|r}
    0 & 0 & -2 & 2 \\
    0 & 0 & 0  & 2 \\
    1 & 1 & 1  & 2
\end{array} \right ]
$$

The row of zeros indicates that, at the point $(0,0,1)$, the second equation does not provide useful information about the direction in which the value of the variables should be adjusted to improve the approximation in the Newton-Raphson iteration. In other words, the variation of the function is zero with respect to small changes in $x$, $y$ and $z$ at that specific point.

## 23

Perform two iterations of Netwton's methods on these systems.

1. Starting with $(0,1)$.

    $$
    F = \left \{ \begin{align*}
        4 { x_1 }^2 - { x_2 }^2       & = 0 \\
        4 { x_1 } { x_2 }^2 - { x_1 } & = 1 \\
    \end{align*} \right . \\[10 pt]

    F = \left \{ \begin{align*}
        4 { x_1 }^2 - { x_2 }^2           & = 0 \\
        4 { x_1 } { x_2 }^2 - { x_1 } - 1 & = 0 \\
    \end{align*} \right . \\[10 pt]

    \begin{bmatrix}
        4 { x_1 }^2 - { x_2 }^2 \\
        4 { x_1 } { x_2 }^2 - { x_1 } - 1\\
    \end{bmatrix}
    =
    \begin{bmatrix}
        0 \\
        0
    \end{bmatrix}
    $$

    $$
    J = \begin{bmatrix}
        8 x_1           & -2 x_2  \\
        4 { x_2 }^2 - 1 & 8 x_1 x_2
    \end{bmatrix}
    $$

    - First iteration.

        $$
        F(0,1) = \begin{bmatrix}
            -1 \\
            -2
        \end{bmatrix}
        $$

        $$
        J(0,1) = \begin{bmatrix}
            0 & -2  \\
            3 & 0
        \end{bmatrix}
        $$

        The final equation for this iteration is

        $$
        \begin{bmatrix}
            0 & -2  \\
            3 & 0
        \end{bmatrix}
        \begin{bmatrix}
            h_1 \\
            h_2
        \end{bmatrix}
        =
        - \begin{bmatrix}
            -1 \\
            -2
        \end{bmatrix}
        =
        \begin{bmatrix}
            1 \\
            2
        \end{bmatrix}
        $$

        $$
        \left [ \begin{array}{rr|r}
            0 & -2 & 1 \\
            3 & 0  & 2 \\
        \end{array} \right ]
        $$

        $$
        -\frac{ F_1 }{ 2 } \rightarrow F_1 \quad
        \left [ \begin{array}{rr|r}
            0 & 1 & -\frac{ 1 }{ 2 } \\
            3 & 0 & 2                \\
        \end{array} \right ] \\[10 pt]

        \frac{ F_2 }{ 3 } \rightarrow F_2\quad
        \left [ \begin{array}{rr|r}
            0 & 1 & -\frac{ 1 }{ 2 } \\
            1 & 0 & \frac{ 2 }{ 3 }  \\
        \end{array} \right ] \\[10 pt]
        $$

        We have found the result of the first iteration.

        $$
        h_1 = \frac{ 2 }{ 3 } \quad h_2 = -\frac{ 1 }{ 2 }
        $$

        The next point is

        $$
        x_1 = 0 + \frac{ 2 }{ 3 } \quad x_2 = 1 + \left (-\frac{ 1 }{ 2 } \right ) = \frac{ 1 }{ 2 } \\[10 pt]

        \left (\frac{ 2 }{ 3 },\frac{ 1 }{ 2 } \right )
        $$

    - Second iteration.

        $$
        F \left (\frac{ 2 }{ 3 },\frac{ 1 }{ 2 } \right ) = \begin{bmatrix}
            \frac{ 55 }{ 36 } \\
            -1
        \end{bmatrix}
        $$

        $$
        J \left (\frac{ 2 }{ 3 },\frac{ 1 }{ 2 } \right ) = \begin{bmatrix}
            \frac{ 16 }{ 3 } & -1  \\
            0                & \frac{ 8 }{ 3 }
        \end{bmatrix}
        $$

        The final equation for this iteration is

        $$
        \begin{bmatrix}
            \frac{ 16 }{ 3 } & -1  \\
            0                & \frac{ 8 }{ 3 }
        \end{bmatrix}
        \begin{bmatrix}
            h_1 \\
            h_2
        \end{bmatrix}
        =
        - \begin{bmatrix}
            \frac{ 55 }{ 36 } \\
            -1
        \end{bmatrix}
        =
        \begin{bmatrix}
            -\frac{ 55 }{ 36 } \\
            1
        \end{bmatrix}
        $$

        $$
        \left [ \begin{array}{rr|r}
            \frac{ 16 }{ 3 } & -1              & -\frac{ 55 }{ 36 } \\
            0                & \frac{ 8 }{ 3 } & 1 \\
        \end{array} \right ]
        $$

        $$
        F_1 + \frac{ 3 }{ 8 } F_2 \rightarrow F_1 \quad
        \left [ \begin{array}{rr|r}
            \frac{ 16 }{ 3 } & 0                & -\frac{ 83 }{ 72 } \\
            0                & \frac{ 8 }{ 3 }  & 1 \\
        \end{array} \right ] \\[10 pt]

        \frac{ 3 }{ 8 } F_2 \rightarrow F_2 \quad
        \left [ \begin{array}{rr|r}
            \frac{ 16 }{ 3 } & 0  & -\frac{ 83 }{ 72 } \\
            0                & 1  & \frac{ 3 }{ 8 } \\
        \end{array} \right ] \\[10 pt]

        \frac{ 3 }{ 16 } F_1 \rightarrow F_1 \quad
        \left [ \begin{array}{rr|r}
            1 & 0 & -\frac{ 83 }{ 384 } \\
            0 & 1 & \frac{ 3 }{ 8 } \\
        \end{array} \right ] \\[10 pt]
        $$

        We have found the result of the second iteration.

        $$
        h_1 = -\frac{ 83 }{ 384 } \quad h_2 = \frac{ 3 }{ 8 }
        $$

        The next point is

        $$
        x_1 = \frac{ 2 }{ 3 } + \left (-\frac{ 83 }{ 384 } \right ) = \frac{ 173 }{ 384 } \quad x_2 = \frac{ 1 }{ 2 } + \frac{ 3 }{ 8 } = \frac{ 7 }{ 8 } \\[10 pt]

        \left (\frac{ 173 }{ 384 },\frac{ 7 }{ 8 } \right )
        $$

2. Starting with $(1,1)$.

    $$
    x = x_1 \quad y = x_2
    $$

    $$
    F = \left \{ \begin{align*}
        x_1 { x_2 }^2 + { x_1 }^2 x_2 + { x_1 }^4         & = 3 \\
        { x_1 }^3 { x_2 }^2 - 2 { x_1 }^5 x_2 + { x_1 }^2 & = -2 \\
    \end{align*} \right . \\[10 pt]

    F = \left \{ \begin{align*}
        x_1 { x_2 }^2 + { x_1 }^2 x_2 + { x_1 }^4 - 3         & = 0 \\
        { x_1 }^3 { x_2 }^2 - 2 { x_1 }^5 x_2 + { x_1 }^2 + 2 & = 0 \\
    \end{align*} \right . \\[10 pt]

    \begin{bmatrix}
        x_1 { x_2 }^2 + { x_1 }^2 x_2 + { x_1 }^4 - 3  \\
        { x_1 }^3 { x_2 }^2 - 2 { x_1 }^5 x_2 + { x_1 }^2 + 2 \\
    \end{bmatrix}
    =
    \begin{bmatrix}
        0 \\
        0
    \end{bmatrix}
    $$

    $$
    J = \begin{bmatrix}
        { x_2 }^2 + 2 x_1 x_2 + 4 { x_1 }^3                    & 2 x_1 x_2 + { x_1 }^2  \\
        3 { x_ 1 }^2 { x_ 2 }^2 - 10 { x_1 }^4 { x_2 } + 2 x_1 & 2 { x_ 1 }^3 x_2 - 2 { x_1 }^5
    \end{bmatrix}
    $$

    - First iteration.

        $$
        F(1,1) = \begin{bmatrix}
            0 \\
            2
        \end{bmatrix}
        $$

        $$
        J(1,1) = \begin{bmatrix}
            7  & 3  \\
            -5 & 0
        \end{bmatrix}
        $$

        The final equation for this iteration is

        $$
        \begin{bmatrix}
            7  & 3  \\
            -5 & 0
        \end{bmatrix}
        \begin{bmatrix}
            h_1 \\
            h_2
        \end{bmatrix}
        =
        - \begin{bmatrix}
            0 \\
            2
        \end{bmatrix}
        =
        \begin{bmatrix}
            0 \\
            -2
        \end{bmatrix}
        $$

        $$
        \left [ \begin{array}{rr|r}
            7  & 3 & 0 \\
            -5 & 0 & -2 \\
        \end{array} \right ]
        $$

        $$
        -\frac{ 1 }{ 5 } F_2 \rightarrow F_2 \quad
        \left [ \begin{array}{rr|r}
            7 & 3 & 0 \\
            1 & 0 & \frac{ 2 }{ 5 } \\
        \end{array} \right ] \\[10 pt]

        F_1 - 7 F_2 \rightarrow F_1
        \quad
        \left [ \begin{array}{rr|r}
            0 & 3 & -\frac{ 14 }{ 5 } \\
            1 & 0 & \frac{ 2 }{ 5 } \\
        \end{array} \right ] \\[10 pt]

        \frac{1}{3} F_1  \rightarrow F_1
        \quad
        \left [ \begin{array}{rr|r}
            0 & 1 & -\frac{ 14 }{ 15 } \\
            1 & 0 & \frac{ 2 }{ 5 } \\
        \end{array} \right ] \\[10 pt]

        F_1 \leftrightarrow F_2
        \quad
        \left [ \begin{array}{rr|r}
            1 & 0 & \frac{ 2 }{ 5 } \\
            0 & 1 & -\frac{ 14 }{ 15 } \\
        \end{array} \right ] \\[10 pt]
        $$

        We have found the result of the first iteration.

        $$
        h_1 = \frac{ 2 }{ 5 } \quad h_2 = -\frac{ 14 }{ 15 }
        $$

        The next point is

        $$
        x_1 = 1 + \frac{ 2 }{ 5 } = \frac{ 7 }{ 5 } \quad x_2 = 1 + \left (-\frac{ 14 }{ 15 } \right ) = \frac{ 1 }{ 15 } \\[10 pt]

        \left (\frac{ 7 }{ 5 },\frac{ 1 }{ 15 } \right )
        $$

    - Second iteration.

        $$
        F \left (\frac{ 7 }{ 5 },\frac{ 1 }{ 15 } \right ) = \begin{bmatrix}
            \frac{ 5504 }{ 5625 } \\[5 pt]
            \frac{ 176008 }{ 140625 }
        \end{bmatrix}
        $$

        $$
        J \left (\frac{ 7 }{ 5 },\frac{ 1 }{ 15 } \right ) = \begin{bmatrix}
            \frac{ 12563 }{ 1125 }  & \frac{ 161 }{ 75 }  \\[5 pt]
            \frac{ 3367 }{ 625 }    & -\frac{ 97412 }{ 9375 }
        \end{bmatrix}
        $$

        The final equation for this iteration is

        $$
        \begin{bmatrix}
            \frac{ 12563 }{ 1125 } & \frac{ 161 }{ 75 } \\[5 pt]
            \frac{ 3367 }{ 625 }   & -\frac{ 97412 }{ 9375 }
        \end{bmatrix}
        \begin{bmatrix}
            h_1 \\
            h_2
        \end{bmatrix}
        =
        - \begin{bmatrix}
            \frac{ 5504 }{ 5625 } \\[5 pt]
            \frac{ 176008 }{ 140625 }
        \end{bmatrix}
        =
        \begin{bmatrix}
            -\frac{ 5504 }{ 5625 } \\[5 pt]
            -\frac{ 176008 }{ 140625 }
        \end{bmatrix}
        $$

        $$
        \left [ \begin{array}{rr|r}
            \frac{ 12563 }{ 1125 } & \frac{ 161 }{ 75 }      & -\frac{ 5504 }{ 5625 } \\[5 pt]
            \frac{ 3367 }{ 625 }   & -\frac{ 97412 }{ 9375 } & -\frac{ 176008 }{ 140625 } \\
        \end{array} \right ]
        $$

        $$
        \left [ \begin{array}{rr|r}
            1 & 0      & -\frac{ 13833512 }{ 24930515 } \\[5 pt]
            0   & 1 & -\frac{ 87553216 }{ 523540815 } \\
        \end{array} \right ]
        $$

        We have found the result of the second iteration.

        $$
        h_1 = -\frac{ 13833512 }{ 24930515 } \quad h_2 = -\frac{ 87553216 }{ 523540815 }
        $$

        The next point is

        $$
        x_1 = \frac{ 7 }{ 5 } + \left (-\frac{ 13833512 }{ 24930515 } \right) \quad x_2 = \frac{ 1 }{ 15 } + \left (-\frac{ 87553216 }{ 523540815 } \right) \\[10 pt]

        \left (\frac{ 7 }{ 5 } + \left (-\frac{ 13833512 }{ 24930515 } \right),\frac{ 1 }{ 15 } + \left (-\frac{ 87553216 }{ 523540815 } \right) \right )
        $$
