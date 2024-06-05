# Number theory

## Divisibilidad

Dados $n,m \in \mathbb{ Z }$, se dice que **$n$ divide a $m$, y se denota $n | m$, si:

$$
n | m \equiv (\exists q \in \mathbb{ Z } : m = n q)
$$

Se dice que:

- $n$ es un **divisor** de $m$.

- $m$ es un **múltiplo** de $n$.

### Propiedades (divisibilidad)

- Si $a | b$ y $a | c$, entonces $a | (b + c)$.

    $$
    \forall a,b,c \in \mathbb{ Z } \quad (a | b \; \land \; a | c) \implies a | (b + c)
    $$

- Si $a | b$, entonces $a | b c$, para todo entero $c$.

    $$
    \forall a,b,c \in \mathbb{ Z } \quad a | b \implies a | b c
    $$

- Si $a | b$ y $b | c$, entonces $a | c$.

    $$
    \forall a,b,c \in \mathbb{ Z } \quad (a | b \; \land \; b | c) \implies a | c
    $$

## Algoritmo de la división

Sea $n$ un número entero y $d$ un entero positivo. Entonces existen **dos enteros $q$ y $r$ únicos**, tal que $0 \leq r < d$, donde:

$$
n = d q + r
$$

- $n$: dividendo.

- $d$: divisor.

- $q$: cociente.

- $r$: residuo.

El enunciado también puede traducirse en:

$$
\forall n \in \mathbb{ Z }, d \in \mathbb{ N }^+ \implies \exists! q,r \in \mathbb{ Z } : (0 \leq r < d) \; \land \; (n = d q + r)
$$

## Número primo

Un número entero positivo $p$ mayor que $1$ es primo **si los únicos factores positivos de $p$ son $1$ y $p$**.

> Un número entero positivo mayor que $1$ que **no** es primo se denomina **compuesto**.

---

### Teorema (número primo)

Si $n$ es un numero compuesto, entonces tiene un divisor primero menor o igual a $\sqrt{ n }$.

$$
\forall n \in \mathbb{ N } \; \land \; n > 1 \; \land \; n \notin \mathbb{ P } \implies \exist p : p \in \mathbb{ P } \; \land \; p | n \; \land p \leq \sqrt { n }
$$

#### Demostración (teorema número primo)

Un número compuesto es un número que tiene al menos un divisor primo distinto de sí mismo y de 1. Si $n$ es un número compuesto, entonces tiene al menos un par de divisores, digamos $a$ y $b$, tal que $n = a * b$.

Si tanto $a$ como $b$ fueran mayores que $\sqrt{ n }$, entonces $a * b$ sería mayor que $n$, lo cual es una contradicción. De manera similar, si tanto $a$ como $b$ fueran menores que $\sqrt{ n }$, entonces $a * b$ sería menor que $n$, lo cual también es una contradicción.

Por lo tanto, si $n = a * b$ para algún par de números $a$ y $b$, entonces necesariamente uno de ellos debe ser menor o igual a $\sqrt{ n }$ y el otro debe ser mayor o igual a $\sqrt{ n }$. Dado que $n$ es un número compuesto, al menos uno de estos números, $a$ o $b$, debe ser un número primo. Por lo tanto, $n$ tiene un divisor primo menor o igual a $\sqrt{ n }$.

## Teorema fundamental de la aritmetica

Todo entero positivo **mayor que $1$** se puede escribir, de **forma única**, como un primo, o como el producto de $2$ o más primos, en el que los **factores primos se escriben de forma creciente**.

## Máximo común divisor (MCD)

Sean $a$ y $b$ enteros diferentes a $0$. El entero más grande $d$, tal que $d | a$ y $d | b$ se denomina máximo común divisor de $a$ y $b$ y se denota por $\operatorname{ MCD }(a,b)$

> Es el número más grande que divide a ambos.

---

Usando los factores primos de $a$ y $b$:

$$
a = p_1^{ a_1 } p_2^{ a_2 } \dots p_n^{ a_n } \\[10 pt]

b = p_1^{ b_1 } p_2^{ b_2 } \dots p_n^{ b_n } \\[10 pt]

\operatorname{ MCD }(a,b) = p_1^{ \operatorname{ min }(a_1,b_1) } p_2^{ \operatorname{ min }(a_2,b_2) } \dots p_n^{ \operatorname{ min }(a_n,b_n) }
$$

## Primo relativo

Un numero entero $a$ es primo relativo de un numero entero $b$ cuando $\operatorname{ MCD }(a,b) = 1$.

## Algoritmo de Euclides

$$
\forall a,b \in \mathbb{ Z } \quad \operatorname{ MCD }(a,b) = \left \{
\begin{array}{lr}
    a                            & b = 0 \\
    \operatorname{ MCD }(b,a\%b) & b \neq 0
\end{array} \right .
$$

### Teorema (algoritmo de Euclides)

Sean $a$ y $b$ dos enteros positivos. Entonces existen dos enteros $s$ y $t$ tales que:

$$
\operatorname{ MCD }(a,b) = a s + b t
$$

Es decir, el máximo común divisor de dos números se puede expresar como una combinación lineal de ellos con coeficientes enteros. En general tenemos lo siguiente:

$$
r_0 = a \quad r_1 = b \\[10 pt]

r_0 = r_1 q_1 + r_2 \\[10 pt]

r_1 = r_2 q_2 + r_3 \\[10 pt]

\vdots \\[10 pt]

r_{ n - 3 } = r_{ n - 2 } q_{ n - 2 } + r_{ n - 1 } \\[10 pt]

r_{ n - 2 } = r_{ n - 1 } q_{ n - 1 } + r_n \\[10 pt]

r_{ n - 1 } = q_n r_n + 0
$$

> $r_n$ corresponde al $\operatorname{ MCD }(a,b)$.

Desde la penúltima ecuación podríamos devolvernos para expresar $r_n$ en términos de $q_0$ y $r_0$.

## Congruencia

Si $a$ y $b$ son enteros y $m$ es un entero positivo, entones $a$ es congruente a $b$ módulo $m$ si, y solo si $a \operatorname{ mod } m = b \operatorname{ mod } m$.

$$
\forall a,b,m \in \mathbb{ Z } \; m > 0 \quad a \equiv b (\operatorname{ mod } m) \iff a \operatorname{ mod } m = b \operatorname{ mod } m
$$

### Propiedades (congruencia)

#### Reflexividad

$$
\forall a,m \in \mathbb{ Z } \; m > 0 \quad a \equiv a (\operatorname{ mod } m)
$$

#### Simetría

$$
\forall a,b,m \in \mathbb{ Z } \; m > 0 \quad a \equiv b (\operatorname{ mod } m) \iff b \equiv a (\operatorname{ mod } m)
$$

#### Transitividad

$$
\forall a,b,m \in \mathbb{ Z } \; m > 0 \quad a \equiv b (\operatorname{ mod } m) \; \land \; b \equiv c (\operatorname{ mod } m) \implies a \equiv c (\operatorname{ mod } m)
$$

### Teorema (congruencia)

$$
\begin{align*}
    a \operatorname{ mod } m = b \operatorname{ mod } m \; \land \; c \operatorname{ mod } m = d \operatorname{ mod } m \implies & \\

             & (a + c) \operatorname{ mod } m = (b + d) \operatorname{ mod } m \\

             & \land \\

             & a c \operatorname{ mod } m = b d \operatorname{ mod } m
\end{align*}
$$