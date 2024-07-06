# Álgebra 3o y 4o enseñanza media

## Preliminares

### Definición

La palabra álgebra se deriva de una voz árabe que significa **reducción**. Esta definición etimológica se acomoda muy bien al álgebra, de la cual se dice que es una ciencia cuyo objeto es la **simplificación** y **generalización** de todas las cuestiones relacionadas con las cantidades.

### Símbolos

Generalmente, se reservan las primeras letras del alfabeto para indicar cantidades conocidas, mientras que las últimas se utilizan para las cantidades desconocidas o incógnitas.

## Unidad I (los números)

### Valor absoluto y valor relativo de los números

- Valor absoluto: es el valor aritmético de dicho número haciendo caso omiso del signo correspondiente.

- Valor relativo: es el valor aritmético de dicho número tomado con el signo correspondiente.

### Números opuestos o simétricos

Son un par de números algebraicos que tienen el mismo valor absoluto, pero difieren en valor relativo.

### Numeros racionales e irracionales

- Numero racional: puede expresarse como el cociente de dos enteros.

- Numero irracional: **no** puede expresarse como el cociente de dos enteros.

Obviamente, el significado semántico de los vocablos racional e irracional no se acomoda en manera alguna a los números aquí estudiados. Todo se debe a un error de traducción. En efecto, Euclides al clasificar sistemáticamente los números los dividió en dos grandes grupos que llamo **symmetros** (con medida) y **asymmetros** (sin medida) respectivamente. Y para señalar el hecho de que los números asymmetros no tenían expresión, los designo con la voz **alogos**. Gerardo de Cremona (1114 - 1187) al traducir un comentario árabe sobre Euclides, tomo los vocablos logos y alogos en su acepción de **razón** y no la de **palabra**, como quiso Euclides, y empleo erróneamente los términos **rationalis** e **irrationalis** para designar unos y otros. Este error se difundió durante toda la edad media hasta llegar a nosotros.

![Numerical sets](./assets/Personal/Álgebra%203o%20y%204o%20enseñanza%20media/1-Numerical_sets.jpg)

## Unidad II (adicción)

### La sustracion algebraica

Para restar un número de otro basta cambiar el signo al número que se va a restar y colocarlo con el nuevo signo enseguida del otro, como en el caso de una suma.

> Obsérvese que después de cambiar el signo al número que se va a restar, todo se reduce a una suma algebraica.

### Leyes de la adicción

1. Ley conmutativa: si $a + b = k$ también $b + a = k$; o $a + b = b + a$; es decir, que los términos se pueden intercambiar sin que se altere el resultado de la adicción.

2. Ley asociativa: si $(a + b) + c = k$, también $a + (b + c) = k$, o $(a + b) + c = a + (b + c)$.

3. Ley de identidad: para cualquier valor de $a$ hay un número y solo uno tal que $a + k = 0$. Tal número $k$ es $0$. Por esta razón, el $0$ recibe el nombre de módulo de la suma o elemento identidad.

## Unidad III (multiplicacion y division)

### Ley conmutativa y ley asociativa

- Ley conmutativa: el orden de los factores no altera el producto.

    $$
    a b = b a
    $$

- Ley asociativa: los factores de un producto pueden ser reagrupados de cualquier modo sin que se altere el producto.

    $$
    a b c = (a b) c = a (b c)
    $$

## Unidad IV (potenciacion r radicacion de enteros)

### Exponente negativo

Veamos como toda cantidad con exponente negativo es una fracción cuyo numerador es uno y su denominador es la misma cantidad elevada a la misma potencia, pero son signo positivo.

$$
\frac{ x^m }{ x^{ m + n } } = x^{ -n } \\[10 pt]

x^{ m + n } = x^m * x^n \\[10 pt]

\frac{ x^m }{ x^{ m + n } } = \frac{ x^m }{ x^m * x^n } = \frac{ 1 }{ x^n }\\[10 pt]

\therefore x^{ -n } = \frac{ 1 }{ x^n }
$$

## Unidad V (expresiones algebraicas)

### La expresión algebraica

Es la representación de una o varias operaciones matemáticas por medio de símbolos. Esto nos lleva a las fórmulas que nos sirven para **generalizar** operaciones matemáticas.

### Termino y sus partes

- Termino: es una expresión algebraica que consta de números y símbolos no separados por los signos $+$ o $-$.
    $$
    a \quad 2 a^2 \quad -12 a b
    $$

### Grado de un término

- Grado absoluto: es la suma de los exponentes de los factores literales.

    $$
    5 a^3 b^2 \quad \text{ Grado $5$ }
    $$

- Grado relativo: con respecto a una letra es el exponente de dicha letra.

    $$
    5 a^3 b^2 \quad \text{ Grado $3$ con respecto a $a$ }
    $$

### Grado de un polinomio

- Grado absoluto: es igual al grado del término que tenga mayor grado.

    $$
    a x + x^4 b^2 - b x^3 + 10 a^2 x^3 \quad \text{ Grado $6$ }
    $$

- Grado relativo: con respecto a una letra es al mayor exponente que tenga dicha letra en el polinomio.

    $$
    a x + x^4 b^2 - b x^3 + 10 a^2 x^3 \quad \text{ Grado $4$ con respecto a $x$  }
    $$

## Unidad VI (adiccion y sustraccion de expresiones algebraicas. Ecuaciones. Inecuaciones)

### Igualdad, identidad. Ecuación

- Igualdad: expresión matemática de dos cantidades que tienen un mismo valor.

- Identidades: igualdad que contiene una o varias cantidades desconocidas llamadas incógnitas que se cumple para cualquier valor que se le dé a las letras.

    $$
    a + b \equiv a + b \\[10 pt]

    x^2 - y^2 \equiv (x + y) (x - y)
    $$

- Ecuación: igualdad que contiene una o varias cantidades desconocidas llamadas incógnitas.

Se llama **primer miembro** de una igualdad o identidad a la expresión que está antes del signo de igualdad y **segundo miembro** a la expresión que va después de dicho símbolo.

Según lo anterior podemos afirmar que toda identidad y ecuación es una igualdad; más no así los recíprocos.

### Grado de una ecuación

Lo determina el término en que la suma de los exponentes de las incógnitas sea máxima.

$$
a^4 x^3 + 2 b x = c \quad \text{ Grado $3$ }
$$

### Principios generales de las ecuaciones

La igualdad subsiste si a los dos miembros de una ecuación se:

- suma o se resta una misma cantidad.

- multiplican o dividen por una misma cantidad.

- elevan a una misma potencia o se les extrae la misma raíz.

### Desigualdades

Llamamos como en las igualdades **primer miembro** a la expresión que está a la izquierda del signo de desigualdad y **segundo miembro** a la expresión que está a la derecha de dicho signo.

#### Propiedades de las desigualdades

- La desigualdad no varía si a los dos miembros de la desigualdad se:

    - suma o resta una misma cantidad.

    - multiplica o divide por una misma cantidad positiva.

- La desigualdad cambia de sentido si a los dos miembros de la desigualdad se:

    - multiplica o divide por una misma cantidad negativa.

    - cambian por sus inversos.

- Si los miembros de una desigualdad son positivos y se elevan a una misma potencia positiva, la desigualdad permanece.

- Si los dos miembros de una desigualdad, o uno de ellos, son negativos y se elevan a una misma potencia impar positiva, la desigualdad permanece.

- Si ambos miembros de una desigualdad, son negativos y se elevan a una misma potencia par positiva, la desigualdad cambia de signo.

- Si los miembros de una desigualdad tienen diferente signo y se elevan a una misma potencia par positiva, la desigualdad **puede** cambiar de signo.

- Si los miembros de una desigualdad son positivos y se les extrae una misma raíz positiva, la desigualdad permanece.

- Si dos o más desigualdades de igual signo se multiplican o suman miembro a miembro, resulta una desigualdad del mismo signo.

- Al restar o dividir miembro a miembro dos desigualdades de igual signo **puede** resultar una igualdad o una desigualdad de diferente signo.

### Inecuaciones

Las desigualdades que contienen una o varias cantidades desconocidas. Las inecuaciones solo se satisfacen para ciertos valores de las incógnitas, por ello se llaman también **desigualdades de condición**.

#### Inecuaciones simultáneas

Aquellas que inecuaciones que tiene una solución común.

## Unidad VII (multiplicación de expresiones algebraicas)

### Ordenación de polinomios

Se dice que un polinomio está ordenado con respecto a una letra cuando los exponentes de dicha letra, llamada **ordenatriz**, van en orden ascendente o descendente.

### Productos notables

Hay ciertos productos que por su simplicidad y por obedecer a reglas fijas se llaman notables y son de la forma $(x \pm y)^2$ y $(x + y)(x - y)$.

1. $(x - y)^2$.

    $$
    \begin{array}{rcl}
    &(x - y)^2 &= &(x + y) (x + y)       \\[5 pt]
    &          &= &x^2 + x y + x y + y^2 \\[5 pt]
    &          &= &x^2 + 2x y + y^2      \\
    \end{array}
    $$

2. $(x - y)^2$.

    $$
    \begin{array}{rcl}
    &(x - y)^2 &= &(x - y) (x - y)       \\[5 pt]
    &          &= &x^2 - x y - x y + y^2 \\[5 pt]
    &          &= &x^2 - 2x y + y^2      \\
    \end{array}
    $$

3. $(x + y)(x - y)$.

    $$
    \begin{array}{rcl}
    &(x + y)(x - y) &= &x^2 + x y - x y + y^2 \\[5 pt]
    &               &= &x^2 - y^2
    \end{array}
    $$

## Unidad VIII (división de expresiones algebraicas)

### División de polinomios

Para dividir un polinomio por otro:

1. Se ordena el polinomio con relación a una letra en orden decreciente.

2. El primer término del cociente resulta de dividir el primer término del dividendo por el primero del divisor.

3. Este primer término del cociente se multiplica por el divisor y el producto se resta del dividendo.

Se repiten estos pasos sucesivamente hasta que el resto sea cero.

### Teorema del residuo. División de un polinomio en $x$ por otro de la forma $(x \pm a)$

Se dice que un polinomio es entero en $x$ cuando todos los exponentes de dicha letra son positivos y enteros.

#### Enunciado

El residuo de la división de un polinomio entero en $x$ por un binomio de la forma $(x \pm a)$ se obtiene reemplazando el polinomio $x$ por $a$, o por $-a$.

En general, si tenemos un polinomio $a x^m + b x^{ m - 1 } + c x^{ m - 2 } + \dots$ dividido por $(x - a)$; y llamamos $Q$ al cociente y $R$ al residuo, luego:

$$
a x^m + b x^{ m - 1 } + c x^{ m - 2 } + \dots = (x - a) Q + R
$$

Reemplacemos $x$ por $a$.

$$
a a^m + b a^{ m - 1 } + c a^{ m - 2 } + \dots = (a - a) Q + R \\[10 pt]

a a^m + b a^{ m - 1 } + c a^{ m - 2 } + \dots = R \\[10 pt]
$$

> Si el divisor es de la forma $(x + a)$ se remplaza $x$ por $-a$.

### Regla de los coeficientes o de Ruffini

$$
{ b x^3 + c x^2 + dx + e } : { x - a }
$$

Si $b_1 x^3 + c_1 x^2 + d_1$ y $R$ son el cociente y el residuo respectivamente resultantes de la división anterior.

$$
\begin{array}{rcl}
    & b x^3 + c x^2 + dx + e & = & (b_1 x^3 + c_1 x^2 + d_1) (x - a) + R \\[5 pt]

    &                        & = & b_1 x^3 + (c_1 a b_1) x^2 + (d_1 - a c_1) x - a d_1 + R
\end{array}
$$

Para que la igualdad anterior sea válida es necesario que los coeficientes de las mismas potencias de $x$ sean iguales.

$$
\begin{array}{rcl}
    & b & = & b_1 \\[5 pt]

    & c & = & c_1 a b_1 \\[5 pt]

    & d & = & d_1 - a c_1 \\[5 pt]

    & e & = & -a d_1 + R
\end{array}
$$

De aquí podemos despejar los coeficientes del cociente y el residuo.

$$
\begin{array}{rcl}
    & b_1 & = & b \\[5 pt]

    & c_1 & = & c + a b_1 \\[5 pt]

    & d_1 & = & d + a c_1 \\[5 pt]

    & R & = & e + a d_1
\end{array}
$$

Esta es la regla de Ruffini para los coeficientes.

1. El primer coeficiente es igual al primero del dividendo.

2. Cualquier otro coeficiente es igual a su correspondiente del dividendo más el producto entre $a$ y el coeficiente inmediatamente anterior del cociente.

3. El resido es igual al último coeficiente del dividendo más el producto entre $a$ y el coeficiente anterior del cociente.

Tanto en el dividendo como en el cociente pueden no estar todas las potencias de $x$, por ello es conveniente adoptar un método que evite confusiones en el cálculo de los coeficientes aplicando la regla de Ruffini. Quizás el más claro sea el de emplear como subíndices las presuntas potencias de $x$ en el cociente, las cuales empiezan por $n - 1$, siendo $n$ la potencia mayor del dividendo.

### Divisibilidad de $x^n \pm a^n$ por $x \pm a$

> Usando el teorema del residuo.

- $x^n - a^n$ siempre es divisible por $x - a$.

    Al reemplazar $x$ por $a$ se anula el polinomio.

    $$
    x^n - a^n = a^n - a^n = 0
    $$

- $x^n - a^n$ es divisible por $x + a$ solo cuando $n$ es par.

    Al reemplazar $x$ por $-a$.

    $$
    x^n - a^n = (-a)^n - a^n
    $$

- $x^n + a^n$ es divisible por $x + a$ solo cuando $n$ es impar.

    Al reemplazar $x$ por $-a$.

    $$
    x^n + a^n = (-a)^n + a^n
    $$

- $x^n + a^n$ nunca es divisible por $x - a$.

    No hay valor posible bajo ninguna circunstancia que haga que $x^n + a^n$ sea $0$.

    > Ni par, ni impar.

## Unidad IX (potenciación)

### Binomio de Newton

Sea un binomio de la forma $(a \pm b)^n$.

1. El número de términos es igual al exponente más uno, o $n + 1$.

2. Los exponentes de $a$ van en orden descendente desde $n$ hasta $0$ y los de $b$ van en orden creciente desde $0$ hasta $n$.

3. La suma de los exponentes de $a$ y $b$ en cualquier término es igual $n$.

4. El coeficiente del primer término es $1$ y el del segundo término es igual al exponente del binomio.

5. Los demás coeficientes se obtienen multiplicando el coeficiente del término anterior por el exponente de $a$ en dicho término y dividiendo el producto por el exponente de $b$ en el mismo término aumentado en $1$.

6. Todos los signos del desarrollo $(a + b)^n$ son positivos; el desarrollo de $(a - b)^n$ tiene signos alternados empezando por positivo.

En general, el coeficiente de cualquier término es igual al producto de todos los exponentes de $a$ en los términos anteriores, dividido por el factorial del exponente de $b$ en dicho término.
$$
(a + b)^n = a^n + n a^{ n - 1 } b + \frac { n (n - 1) a^{ n - 2 } b^2 }{ 2! } + \dots + n a b^{ n - 1 } + b^n
$$

### Cuadrado de un polinomio

Sea un polinomio $p$ en el desarrollo de su cuadrado ($p^2$) se cumple lo siguiente:

1. El desarrollo contiene el cuadrado de todos y cada uno de los terminos del polinomio siempre con signo positivo.

2. Luego aparecen en el desarrollo todos los dobles productos de las posibles combinaciones binaria que pueden hacerse entre los terminos del polinomio.

3. Los signos de los dobles productos depende del que tengan sus terminos en el polinomio, de acuerdo con las leyes de la multiplicacion.

## Unidad X (factorización)

### Formación de cuadrados perfectos

### Factorización por inspección