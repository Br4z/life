# Relations

Sean $A$ y $B$ conjuntos, una relación binaria definida de $A$ en $B$ es un subconjunto de $A \times B$.

$$
R = \{(a,b) \; | \; a \in A, b \in B\}
$$

> Otra notacion es $aRb$.

## Propiedades

### Reflexiva

Una relación $R$ definida en el conjunto $A$ es reflexiva si:

$$
\forall a \in A \quad (a,a) \in R
$$

### Irreflexiva

Una relación $R$ definida en el conjunto $A$ es irreflexiva si:

$$
\forall a \in A \quad (a,a) \notin R
$$

### Simétrica

Una relación $R$ definida en el conjunto $A$ es simétrica si:

$$
\forall a,b \quad ((a,b) \in R \implies (b,a) \in R)
$$

### Antisimétrica

Una relación $R$ definida en el conjunto $A$ es antisimétrica si:

$$
\forall a,b \quad ((a,b) \in R \implies (b,a) \notin R) \\[10 pt]

\forall a,b \quad (((a,b) \in R \; \land \; (b,a) \in R) \implies a = b)
$$

### Transitiva

Una relación $R$ definida en el conjunto $A$ es transitiva si:

$$
\forall a,b,c \quad (((a,b) \in R \; \land \; (b,c) \in R) \implies (a,c) \in R)
$$

### Equivalencia

Una relación $R$ definida en el conjunto $A$ es de equivalencia si:

$$
(\forall a \in A \quad (a,a) \in R) \; \land \; (\forall a,b \quad ((a,b) \in R \implies (b,a) \in R)) \; \land \; (\forall a,b,c \quad (((a,b) \in R \; \land \; (b,c) \in R) \implies (a,c) \in R))
$$

> Es decir, es reflexiva, simétrica y transitiva.

### Orden parcial

Una relación $R$ definida en el conjunto $A$ es de orden parcial si:

$$
(\forall a \in A \quad (a,a) \in R) \; \land \; (\forall a,b \quad ((a,b) \in R \implies (b,a) \notin R)) \; \land \; (\forall a,b,c \quad (((a,b) \in R \; \land \; (b,c) \in R) \implies (a,c) \in R))
$$

> Es decir, es reflexiva, antisimétrica y transitiva.
