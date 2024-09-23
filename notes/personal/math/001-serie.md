# Serie

## Properties

### Commutative

$$
\sum_{ k = 1 }^n (a_k + b_k) = \sum_{ k = 1 }^n (b_k + a_k)
$$

### Associative

$$
\sum_{ k = 1 }^n (a_k + b_k)  + \sum_{ k = 1 }^n c_k = \sum_{ k = 1 }^n a_k + \sum_{ k = 1 }^n (b_k + c_k) \\[10 pt]

\sum_{ k = 1 }^n (a_k + b_k + c_k)
$$

### Distributive

$$
c * \sum_{ k = 1 }^n a_k = \sum_{ k = 1 }^n (c * a_k)
$$

### Constant value

$$
\sum_{ k = 1 }^n c = n * c
$$

### Separation

$$
\sum_{ k = 1 }^n a_k = \sum_{ k = 1 }^{ n_0 } a_k + \sum_{ k = n_0 + 1 }^n a_k
$$

### Examples

1. $\sum_{ k = 1 }^n (ca_k + b_k)$.

    $$
    c * \sum_{ k = 1 }^n a_k + \sum_{ k = 1 }^n b_k
    $$

## Demostrations

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ i = 0 }^n { 2^i } = 2^{ n - 1 } - 1$

### Base case ($\sum_{ i = 0 }^n { 2^i } = 2^{ n - 1 } - 1$)

$$
\sum_{ i = 0 }^{ n = 0 } { 2^i } = 2^{ n + 1 } - 1 \quad 2^0 = 2^{ 0 + 1 } - 1 \quad 1 = 1
$$

### Induction case ($\sum_{ i = 0 }^n { 2^i } = 2^{ n - 1 } - 1$)

$$
\sum_{ i = n + 1 }^{ n + 1 } { 2^i } = 2^{ (n + 1) + 1 } - 1 \quad 2^0 + 2^1 + \dots + 2^n + 2^{ n + 1 } = 2^{ n + 2 } - 1 \\[10 pt]

\underbrace{ 2^{ n + 1 } - 1 }_{ 2^0 + 2^1 + \dots + 2^n } + 2^{ n + 1 } = (2^{ n + 1 } + 2^{ n + 1 }) - 1 = 2^{ n + 1 } (1 + 1) - 1 = 2^{ n + 2 } - 1
$$

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 1 }^n k = \frac{ n (n + 1) }{ 2 }$ (arithmetic series)

$$
\begin{array}{lcr}
    S   & = & 1 + 2 + \dots + (n - 1) + n \\[10 pt]
    S   & = & (n - 1) + (n - 2) + \dots + (n - (n - 1)) \\[10 pt]
    \hline
    2 S & = & n^2 + n
\end{array} \\[10 pt]

S = \frac{ n^2 + n }{ 2 } = \frac{ n (n + 1) }{ 2 }
$$

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 1 }^n k^2 = \frac{ n (n + 1) (2n + 1) }{ 6 }$ (square series)

- $a^3 - b^3 = (a -b) (a^2 + a b + b^2)$.

$$
\begin{array}{lcr}
    n^3 - (n - 1)^3                         & = & (n - (n - 1)) (n^2 + n (n - 1) + (n - 1)^2) \\[10 pt]
                                            & = & n^2 + n^2 - n + n^2 - 2 n + 1 \\[10 pt]
                                            & = & 3 n^2 - 3 n + 1  \\[10 pt]
    (n - 1)^3 - ((n -1) - 1)^3              & = & 3 (n - 1)^2 - 3 (n - 1) + 1 \\[10 pt]
    (n - 2)^3 - ((n -2) - 1)^3              & = & 3 (n - 2)^2 - 3 (n - 2) + 1 \\[10 pt]
    \vdots                                  &   & \\[10 pt]
    (n - (n - 1))^3 - ((n - (n - 1)) - 1)^3 & = & 3 (1)^2 - 3 (1) + 1
\end{array} \\[10 pt]
$$

If we observe, the second term of the subtraction cancels with the first term of the next element, for example, the $-(n - 1)^3$  of the first element and the $(n - 1)^3$ of the second element.

$$
n^3 = 3 \sum_{ n = 1 }^n n^2 - 3 \sum_{ n = 1 }^n n + n \quad \sum_{ n = 1 }^n n^2 = \frac{ 1 }{ 3 } \left (n^3 + 3 \sum_{ n = 1 }^n n - n \right ) \\[10 pt]

\frac{ n }{ 3 } \left (n^2 + 3 \frac{ (n + 1) }{ 2 } - 1 \right ) = \frac{ n }{ 3 } \left (\frac{ 2 n^2 + 3 n + 3 - 2 }{ 2 } \right ) = \frac{ n }{ 3 } \left (\frac{ (2 n + 1) (n + 1) }{ 2 } \right ) \\[10 pt]

\frac{ n (2 n + 1) (n + 1) }{ 6 }
$$

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 1 }^n k^3 = \frac{ n^2 (n + 1)^2 }{ 4 }$ (cube series)

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 0 }^n x^k = \frac{ x^{ n + 1 } - 1 }{ x - 1 }$ (geometric series)

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 0 }^\infty x^k = \frac{ 1 }{ 1 - x } \quad |x| < 1$ (geometric series)

## $\forall{ n } \in \mathbb{ N }^*$ satisfied that $\sum_{ k = 1 }^{ n } \frac{ 1 }{ k } = \ln n +$ (harmonic series)
