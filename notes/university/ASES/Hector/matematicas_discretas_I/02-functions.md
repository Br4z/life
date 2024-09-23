# Functions

Una función permite **representar la relación** entre dos conjuntos. Dados dos conjuntos $A$ y $B$, una función total $f$ de $A$ a $B$, denotada como $f: A \rightarrow B$, **asigna a cada elemento** de $A$ **exactamente un elemento** de $B$.

## Dominio, codominio y rango

Si $f$ es una función de $A$ a $B$, se dice que:

- $A$ es el dominio.

- $B$ es el codominio.

- El rango ($R$) de $f$ es el conjunto de todas las imágenes de los elementos de $A$, es decir, $R \subseteq B$.

## Tipos de funciones

### Inyectiva

Una función $f$ se llama **uno a uno** o **inyectiva**, si y solo si, cada imagen asociada es única.

$$
\forall a,b \quad (f(a) = f(b) \implies a = b) \\[10 pt]

\forall a,b \quad (a \neq b \implies f(a) \neq f(b))
$$

> Es decir, son funciones que **nunca** asocian **dos elementos diferentes** del dominio con **un mismo valor** del codominio.

### Sobreyectiva

Una función $f$ es sobreyectiva, **si y solo si**, para cada elemento $b \in B$ (codominio), existe un elemento $a \in A$ (dominio) tal que $f(a) = b$.

> En este caso se cumple que el codominio **es igual** al rango.

$$
\forall y \; \exists x \quad (f(x) = y)
$$

### Biyectiva

Una función $f$ es biyectiva si es **inyectiva** y **sobreyectiva**.

$$
(\forall a,b \quad (f(a) = f(b) \implies a = b)) \; \land \; (\forall y \; \exists x \; (f(x) = y))
$$
