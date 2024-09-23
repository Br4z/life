# Introduction to parallel programming

## Introducción

La paralelización automática funciona, pero algunos detalles aún se les escapan. Programar en paralelo implica un **conocimiento** importante del hardware del computador.

## Pensando en paralelo

La programación secuencial es natural, pero es inadecuada para las nuevas arquitecturas de cómputo.

La propuesta de **patrones estructurados paralelos** permite concentrarse en la solución del problema e ignorar los detalles de implementación. Estos patrones reducen el **no-determinismo** que es común en la programación paralela.

> Como lo son "Pthread" y "OpenMP".

## Trampas secuenciales

El objetivo de un programador de aplicaciones paralelas es encontrar las partes del código que puedan ser paralelizables. Sin embargo, debido a su naturaleza, habrá partes del código que **no** se pueden paralelizar, o al menos no se debería si no se quiere un funcionamiento **inesperado**.

Las trampas seriales son aquellas partes del código que parecieran deben ser secuenciales, pero no lo deben ser.

## Rendimiento

El objetivo a la hora de paralelizar un algoritmo es minimizar su **span** o tiempo de ejecución. Al span se le conoce también como la **ruta crítica** y nos indica el tiempo más largo que toma ejecutar alguna de las computaciones en paralelo dentro del programa.

Una forma de reducir el span es a través de la reducción de la comunicación o acceso a los datos.

## Memoria compartida, localidad y caché

### Localidad de referencia

Se refiere a la tendencia del programa informático a acceder a instrucciones cuyas direcciones están cerca unas de otras.

### Operación de caché

Se basa en el principio de localidad de referencia. Hay dos formas de obtener datos o instrucciones de la memoria principal y almacenarlos en la memoria caché.

#### Localidad temporal

Los datos o instrucciones que se están obteniendo pueden necesitarse pronto. Por lo tanto, debemos almacenar esos datos o instrucciones en la memoria caché para evitar tener que volver a buscar los mismos datos en la memoria principal.

#### Localidad espacial

Significa que la instrucción o los datos cercanos a la posición de memoria actual que se están obteniendo pueden ser necesarios en un futuro próximo.

#### Rendimiento de la caché

Cuando la CPU consulta la memoria y encuentra el dato o la instrucción en la memoria caché, se denomina acierto (**hit**) de caché. Si los datos o la instrucción deseados no se encuentran en la memoria caché y la CPU recurre a la memoria principal para encontrar dichos datos o instrucción, se conoce como fallo (**miss**) de caché.

$$
\text{hit} + \text{miss}  = \text{total CPU reference} \\[10 pt]

\text{hit ratio} = h = \frac{ \text{hit} }{ \text{hit} + \text{miss} } \\[10 pt]

\text{miss ratio} = 1 - \text{hit ratio} = \frac{ \text{miss} }{ \text{hit} + \text{miss} }
$$

El tiempo de acceso a memoria consta de dos niveles: memoria caché y memoria principal. Si $T_c$ es el tiempo de acceso a la memoria caché y $T_m$ es el tiempo de acceso a la memoria principal, entonces podemos escribir:

##### Acceso simultáneo

$$
T_{ \text{avg} } = h * T_c + (1 - h) T_m
$$

##### Acceso jerárquico

En un sistema de memoria con múltiples niveles (por ejemplo, caché L1 y L2, además de la memoria principal), el tiempo de acceso promedio se calcula de manera similar al caso simultáneo, pero con la consideración de que, en caso de fallo, se debe acceder al nivel superior de la jerarquía de memoria antes de acceder a la memoria principal.

$$
T_{ \text{avg} } = h * T_c + (1 - h) (T_m + Tc)
$$

## Ley de Amdahl

Gene Amdahl estableció una ley que define un límite inferior, el cual una tarea por más elementos de procesamiento que se le involucren, no podrá reducir su tiempo de cómputo.

> La mejora obtenida en el rendimiento de un sistema debido a la alteración de uno de sus componentes está limitada por la fracción de tiempo que se utiliza dicho componente.

$$
S_\text{latency}(s) = \frac{ T_o }{ T_n } = \frac{ T }{ (1 - p) T + \frac{ p }{ s } T } = \frac{ T }{ (1 - p) + \frac{ p }{ s } }
$$

- $T_o$: tiempo original de ejecución.

- $T_n$: nuevo tiempo de ejecución.

- $s$: factor de paralelización.

- $p$: proporción de código paralelizable.

> Se debe ser estratégico a la hora de decidir donde invertir tu esfuerzo para paralelizar.

## Nacimiento del paralelismo

### Cantidad de transistores por procesador

La ley de Moore:

- $1965$: Gordon Moore afirmó que la tecnología tenía futuro, que el número de transistores por unidad de superficie en circuitos integrados se duplicaba cada año y que la tendencia continuaría durante las siguientes dos décadas.

- $1975$: modificó su propia ley al corroborar que el ritmo bajaría, y que la capacidad de integración no se duplicaría cada $12$ meses, sino cada $24$ meses aproximadamente.

- $2007$: determinó una fecha de caducidad de $10$ a $15$ años.

### Frecuencia de reloj del procesador

Las tasas de reloj venían incrementando ($1997$ - $2003$), pero ahora se han estabilizado alrededor de los $3 \text{GHz}$. Su estabilización es debido a:

- Power wall: consumo exagerado de parte del procesador.

    > La tasa de consumo de energía no crece a la misma tasa del reloj del computador.

- Memory wall: discrepancias entre las velocidades del procesador y las memorias.

    > Las tasas de acceso a memoria no crecen tan rápido como la tasa de procesamiento de la CPU.

- Intruction Level Parallelism (ILP) wall: limites al paralelismo de bajo nivel.

## Los patrones de software en paralelismo

Nacen de estructurar las soluciones "mejor conocidas" a ciertos problemas y se empaquetan para ser usadas en aplicaciones paralelas eficientes.

- Ofrecen un **vocabulario** que permite la fácil comunicación de algoritmos y nuevos diseños de aplicaciones.

- Nos permiten crear soluciones de **alto nivel** a problemas complejos.

### ¿Qué significa soluciones de alto nivel?

Significa crear soluciones de software **escalables** capaces de responder en entornos de dos, cuatro o decenas de núcleos con poca o ninguna modificación. Siendo posible obviando ciertos detalles de implementación (como en librerías o hardware).
