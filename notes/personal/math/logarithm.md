# Logarithm

## Definition

$$
\log_b a = c \rightarrow b^c = a \quad b,a \in \mathbb{ R } > 0
$$

## Properties

1. $\log_b b = 1 \rightarrow b^1 = b$.

2. $\log_b 1 = 0 \rightarrow b^0 = 1$.

3. $b^{ \log_b a } = a \rightarrow \log_b a = \log_b a$.

4. $\log_b a^n = n * \log_b a$.

    $$
    b^{ n\log a } = a^n \quad a^n = (b^{ \log a })^n \quad a^n = a^n
    $$

5. $\log_b ac = \log_b a + \log_b c$.

    $$
    \begin{array}{lr}
        p = \log_b a & q = \log_b c \\[5 pt]
        a = b^p      & c = b^q
    \end{array} \\[10 pt]

    \log_b { b^p * b^q } = \log_b b^{ p + q } \\[10 pt]

    (p + q) \log_b b = p + q = \log_b a + \log_b c
    $$

6. $\log_b \frac{ a }{ c } = \log_b a - \log_b c$.

    $$
    \log_b a c^{ -1 } = \log_b a + \log_b c^{ -1 } = \log_b a - \log_b c
    $$

7. $\log_b a = \frac{ \log_c a }{ \log_c b } \quad b \neq 1$.

    $$
    \log_c a = \log_c b^c \quad \text {can be done because $log$ is an injective function} \\[10 pt]

    \log_c a = c \log_c b \quad \log_c a = \log_b a \log_c b \quad \log_b a = \frac{ \log_c a }{ \log_c b }
    $$

8. $n^{ \log_y x } = x^{ \log_y n } \quad \{n,x,y\} \in \mathbb{ N } \; \land \; y \neq 1$.

    $$
    \log_y(n^{ \log_y x }) = \log_y(x^{ \log_y n }) \quad \log_y x \log_y n = \log_y n \log_y x \\[10 pt]

    \text{we divide both sides by $log_y n \neq 0$} \\[10 pt]

    \frac{ \log_y x \log_y n }{ \log_y n } = \frac{ \log_y n \log_y x }{ \log_y n } \quad \log_y x = \log_y x
    $$
