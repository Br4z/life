# Sequence

A succession (or progression) is a discrete structure used to represent **lists** of numbers in a **specific order**. The notation $\{ a_n \}$ is often used to denote a sequence, where $a_n$ refers to the element of the sequence at position $n$, called the general term. The subscript $n \in \mathbb{ N }$ indicates the place it occupies in that sequence.

A numerical sequence is formalized as an application of the natural numbers on another numerical set $X$.

$$
\begin{array}{rccl}
    a: & \mathbb { N } & \longrightarrow & X \\
       &  n            & \longmapsto     & a_{ n }
\end{array}
$$

## Arithmetic sequence

Is a sequence of numbers such that the difference from any succeeding term to its preceding term remains constant throughout the sequence. The constant difference is called common difference of that arithmetic progression.

$$
a_n = a_1 + n (d - 1)
$$

- $a_1$: initial term of an arithmetic sequence.

- $d$: the common difference of successive members.

### Sum

The sum of the members of a finite arithmetic progression is called an **arithmetic series**.

$$
S_n = a_1 + a_2 + \dots + a_{ n - 1 } + a_n \quad (2) \\[10 pt]

S_n = a_1 + (a_1 + d) \dots + (a_1 + (n - 2) d) + (a_1 + (n - 1) d) \quad (2)
$$

Rewriting the terms in reverse order of $(2)$.

$$
S_n = (a_1 + (n - 1) d) + (a_1 + (n - 2) d) + \dots + (a_1 + d) + a_1
$$

Adding $(2)$ and $(3)$.

$$
\begin{array}{lcr}
    S_n   & = & a_1 + (a_1 + d) \dots + (a_1 + (n - 2) d) + (a_1 + (n - 1) d) \\[10 pt]
    S_n   & = & (a_1 + (n - 1) d) + (a_1 + (n - 2) d) + \dots + (a_1 + d) + a_1 \\[10 pt]
    \hline
    2 S_n & = & n (2 a_1 + (n - 1) d)
\end{array} \\[10 pt]

S_n = \frac{ n }{ 2 } (2 a_1 + (n - 1) d) \quad (4)
$$

Rewriting $(4)$.

$$
S_n = n \frac{ a_1 + a_1 + (n - 1) d }{ 2 } = n \frac{ a_1 + a_n }{ 2 }
$$

[Gauss sum](./serie.md#satisfied-that--arithmetic-series)

## Geometric sequence

Is a sequence of numbers where each term after the first is found by multiplying the previous one by a fixed, non-zero number called the common **ratio**.

$$
a_n = a_1 r^{ n - 1 }
$$

- $a_1$: initial term of a geometric sequence.

- $r$: the **ratio** of a geometric sequence.

This sequence follows the recursive relation.

$$
a_n = r a_{ n - 1 } \quad n \in \mathbb{ N } \; n \geq 2
$$
