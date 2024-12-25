---
reviewed_on: "2024-12-01"
---

# Data minig - clasification

## Requisitos (clasificación)

- Suministrar el atributo de **decisión** o clase (**label**).

- Suministrar los atributos de **condición**, estos atributos son usados para describir por medio del proceso de inducción las **clases**.

## Matriz de confusión

|                   |   **Actual yes**    |    **Actual no**    |
|:-----------------:|:-------------------:|:-------------------:|
| **Predicted yes** | true positive (TP)  | false positive (FP) |
| **Predicted no**  | false negative (FN) | true negative (TN)  |

[useful metrics of a confusion matrix](../../../../../personal/computer_science/machine_learning/metrics.md).

## Técnicas (clasificación)

### Árboles de decisión

- Nodos: representan la verificación de una condición sobre un atributo.

- Ramas: representan el valor de la condición comprobada en el **nodo** del cual derivan.

- Nodo hoja: representan las etiquetas de clase.

#### Algoritmo básico (voraz)

- El árbol se construye de forma **top-down** recursivamente utilizando **divide y vencerás**.

- Al principio, todas las tuplas se encuentran en la raíz.

- Los atributos deben ser **categoricos**, si son valores continuos hay que **discretizarlos** previamente.

- Las tuplas se van dividiendo recursivamente con base el atributo seleccionado.

- Los atributos de condición se seleccionan con base en estadísticas o mediante medidas estadísticas.

#### Ganancia de informacion

Para seleccionar el atributo con mayor ganancia de información. Si hay dos clases $P$ y $N$, sea el conjunto de ejemplos $S$ que contiene $p$ elementos de la clase $P$ y $n$ elementos de la clase $N$. La cantidad de información que se necesita para decidir si una muestra cualquiera de $S$ pertenece a $P$ o a $N$ se define como:

$$
\operatorname{ I }(p,n) = -\frac{ p }{ p + n } \log_2 \frac{ p }{ p + n } - \frac{ n }{ p + n } \log_2 \frac{ n }{ p + n }
$$

> A esto se le llama **entropía**.

- Maximo: cuando la probabilidad de las dos clases es la misma.

    $$
    \text{entropy}_\text{max} = -0.5 \log_2 0.5 - (-0.5 \log_2 0.5) = 1
    $$

- Minima (**nodo puro**): cuando todas las probabilidades estan en una clase.

    $$
    \text{entropy}_\text{max} = -1 \log_2 1 = 0
    $$

La división óptima se obtiene eligiendo la **característica** con **menor entropía**.

---

Si se utiliza un atributo $A$, un conjunto $S$ se dividira en conjuntos $\{S_1,S_2,\dots,S_v\}$. Si $S_i$ contiene $p_i$ elementos de $P$ y $n_i$ elementos de $N$, la entropia, o la informacion necesaria para clasificar objetos en todos los subarboles $S_i$ es

$$
E(A) = \sum_{ i = 1 }^v { \frac{ p_i + n_i }{ p + n } I(p_i, p_n) }
$$

La ganancia de inforcion de la rama $A$ es

$$
\textoperator{Gain}(A) = I(p,n) - E(A)
$$

### Clasificación Naïve Bayes

Este modelo hace la suposición de que los atributos son condicionalmente independientes. La probabilidad de que un ejemplo pertenezca a una clase $C_j$ dado un conjunto de valores de características $V = \{v_1,v_2,\dots,v_n\}$ se calcula como:

$$
P(C_j|V) = P(C_j) \prod_{ i = 1 }^n P(v_i|C_j)
$$

- $P(C_j|V)$: la probabilidad de que el ejemplo pertenezca a la clase $C_j$ dado las características $V$ (esto se llama probabilidad **a posteriori**).

- $P(C_j)$: la probabilidad previa de la clase $C_j$ (sin observar ningún dato).

- $P(v_i|C_j)$: la probabilidad de observar el valor de la característica $v_i$ dado que la clase es $C_j$. Este valor se estima generalmente a partir de los datos de entrenamiento.

- $\prod_{ i = 1 }^n$: Esto representa el producto de las probabilidades individuales de cada característica $v_i$, suponiendo independencia condicional entre ellas.

#### Teorema de Bayes

Dado un conjunto de datos, la probabilidad a posteriori de una hipótesis $h$ es

$$
P(h|D) =\frac{ P(D|h) p(h) }{ P(D) }
$$

- $P(h)$: probabilidad apriori de la hipótesis $h$.

- $P(D)$: probabilidad apriori de los datos de entrenamiento $D$.

- $P(h|D)$: probabilidad de $h$ dado $D$.

- $P(D|h)$: probabilidad de $D$ dado $h$.
