# Recursion

## mcdTFA

Queremos demostrar qué $\forall n,m \in \mathbf{N} : mcdTFA(n,m) = MCD(n,m)$.

### Caso base

```Scala
if(primes.isEmpty) 1
```

Cuando no quede elementos en la lista de los primos, significara que no quedan elementos en las demás, por lo tanto retorno el neutro de la multiplicación $1$.

Que retorne $1$ cuando se ingresen listas vacías no tiene ningún significado.

### Argumentación

Por consecuencia del **teorema fundamental de la aritmética** sabemos que:

$$
n = p_1^{i_1} * p_2^{i_2} * \ldots * p_k^{i_k} \quad m = p_1^{j_1} * p_2^{j_2} * \ldots * p_k^{j_k} \quad (1) \\[5 pt]

mcd(n,m) = p_1^{min(i_1,j_1)} * p_2^{min(i_2,j_2)} * \ldots p_k^{min(i_k,j_k)} \quad (2)
$$

En $(1)$ $n$ y $m$ son los números que representan las listas `ln` y `lm` respectivamente.

La operación de $(2)$ la hago en la siguiente lineas de código:

```Scala
else Math.pow(primes.head, (ln.head).min(lm.head)).toInt * mcdTFA(ln.tail, lm.tail, primes.tail)
```

## GCD with Bezout coefficients

```SCALA
def GCD_Bezout(n : Int, m : Int) : (Int, Int, Int) = {
    if (m == 0)
        (n, 1, 0)
    else {
        val (d, x1, y1) = GCD_Bezout(m, n % m)

        (d, y1, x1 - n / m * y1)
    }
}
```

At each step, update the Bezout coefficients. If in the previous recursion we have found the GCD $d$ and the coefficients $x_1$ and $y_1$ such that:

$$
d = m x_1 + n \% m y_1 \quad (1).
$$

By definition, we know that:

$$
n \% m = n - \frac{ n }{ m } m \quad (2)
$$

> Keeping only the int part of $\frac{ n }{ m }$.

Substituting $(2)$ into $(1)$.

$$
d = m x_1 + \left (n - \frac{ n }{ m } m \right ) y_1 = n y_1 + m \left (x_1 - \frac{ n }{ m } y_1 \right )
$$

We have found that the new coefficients are $y_1$ and $x_1 - \frac{ n }{ m } y_1$.

## Tree recursion Fibonacci

Queremos demostrar qué $\forall n \in \mathbb{N} : fibonacciA(n) = fib(n)$.

### Casos base

1. `fibonacciA(0) == fib(0) = 1`

   ```Scala
    fibonacciA(0) {
        if(0 <= 1) 1
        else fibonacciA(0 - 1) + fibonacciA(0 - 2)
    }
    //fibonacciA(0) = 1
   ```

2. `fibonacciA(1) == fib(1) = 1`

    ```Scala
    fibonacciA(1) {
        if(1 <= 1) 1
        else fibonacciA(1 - 1) + fibonacciA(1 - 2)
    }
    //fibonacciA(1) = 1
    ```

### Inducción

**Hipótesis** `fibonacciA(n) == fib(n)` $\Rightarrow$ `fibonacciA(n + 1) == fib(n + 1)`

### Demostración

```Scala
fibonacciA(n + 1) {
    if(n + 1 <= 1) 1
    else fibonacciA((n + 1) - 1) + fibonacciA((n + 1) - 2)
}
//fibonacciA(n + 1) = fibonacciA(n) + fibonacciA(n - 1)
```

**Definición** $\Rightarrow fib(n + 1)$.

Por lo que acabamos de demostrar qué la **hipótesis**.


## Iterative Fibonacci

```SCALA
def iterative_fibonacci(N : Int) = {
    def aux(n : Int, a : Int, b : Int) : Int = {
        if (n == 0)
            a
        else
            aux(n - 1, b, a + b)
    }
    aux(N, 0, 1)
}
```

We will demonstrate that $\forall n \in \mathbb{N} : \operatorname{ iterative\_fibonacci }(n) = \operatorname{ fib }(n)$.

- State: $S_i = (n,a,b)$.

- Initial state: $s_0 = (N,1,1)$.

- Final state: $s_f = (0,a,b)$.

- Invariant: $(i,a,b) : a = \operatorname{ fib }(i) \land b = \operatorname{ fib }(i + 1)$.

    > $i = N - n$.

- Transformation: $(n,a,b) : (i + 1,b,a + b)$.

### $\operatorname{ inv }(s_0)$

$$
\operatorname{ inv }((N,0,1)) : 0 = \operatorname{ fib }(N - N) \; \land \; 1 = \operatorname{ fib }(N - N + 1) \\[10 pt]
0 = \operatorname{ fib }(0) \; \land \; 1 = \operatorname{ fib }(1) \\[10 pt]

\operatorname{ inv }((N,0,1)) \rightarrow True
$$

### $(s_i \neq s_f \; \land \; \operatorname{ inv }(s_f)) \rightarrow \operatorname{ inv }(\operatorname{ trans }(s_i))$

- $s_i \neq s_f$: $n \geq 0 \rightarrow i \leq N$

- $\operatorname{ inv }(s_f)$: $(\operatorname{ inv }((i,a,b)): a = \operatorname{ fib }(i) \; \land \; b = \operatorname{ fib }(i + 1))$.

$$
\operatorname{ inv }(\operatorname{ trans }(s_i)) = \operatorname{ inv }(\operatorname{ trans }(i,a,b)) = \operatorname{ inv }(i + 1,b,a + b) \\[10 pt]

b = \operatorname{ fib }(i + 1) \; \land \; a + b = \operatorname{ fib }((i + 1) + 1) \\[10 pt]

b = \operatorname{ fib }(i + 1) \; \land \; \operatorname{ fib }(i) + \operatorname{ fib }(i + 1) = \operatorname{ fib }(i + 2) \\[10 pt]
$$

### $\operatorname{ inv }((s_f)) \rightarrow \operatorname{ answer }(s_f) = \operatorname{ fib }(n)$

$$
\operatorname{ inv }(N,a,b) \rightarrow a  == \operatorname{ fib }(N) \\[10 pt]

(a = \operatorname{ fib }(N) \land b = \operatorname{ fib }(N + 1)) \rightarrow a == \operatorname{ fib }(N) \rightarrow True
$$

> In propositional logic, if the antecedent already includes the consequent as part of it, the implication is trivially true.
