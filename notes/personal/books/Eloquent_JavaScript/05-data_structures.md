# Data structures: objects and arrays

> "On two occasions I have been asked, "Pray, Mr. Babbage, if you put into the machine wrong figures, will the right answers come out?" \[...\] I am not able rightly to apprehend the kind of confusion of ideas that could provoke such a question." - Charles Babbage, Passages from the Life of a Philosopher (1864).

---

Numbers, Booleans, and strings are the atoms from which data structures are built. Many types of information require more than one atom, though. **Objects** allow us to group values (including other objects) to build more complex structures.

## Datasets

...Zero-based counting has a long tradition in technology and in certain ways makes a lot of sense, but it takes some getting used to. Think of the index as the number of items to skip, counting from the start of the array.

## Properties

The two main ways to access properties in JavaScript are with a dot and with square brackets. Both `value.x` and `value[x]` access a property on value, but not necessarily the same property. The difference is in how `x` is interpreted. When using a dot, the word after the dot is the literal name of the property. When using square brackets, the expression between the brackets is **evaluated** to get the property name. Whereas `value.x` fetches the property of value named "x", `value[x]` takes the value of the variable named "x" and uses that, converted to a string, as the property name.

## Methods

Properties that contain functions are generally called **methods** of the value they belong to...

> Un ejemplo es `toUpperCase` (método de string).

## Objects

Reading a property that does not exist will give `undefined`.

It is possible to assign a value to a property expression with the `=` . This will replace the property's value if it already existed or create a new property on the object if it didn’t.

...`delete` ...It is a unary operator that, when applied to an object property, will remove the named property from the object.

...`binary` in operator, when applied to a string and an object, tells you whether that object has a property with that name.

To find out what properties an object has, you can use the `Object.keys`. Give the function an object and it will return an array of strings (the object's property names).

`Object.assign` that copies all properties from one object into another:

Los arrays son, entonces, solo un tipo de objeto especializado para almacenar secuencias de cosas. Si evalúas `typeof([])`, este produce `object`.

## Mutability

Vimos que los valores de objeto pueden ser modificados. Los tipos de valores discutidos en capítulos anteriores, como números, strings y booleanos, son todos **inmutables**, es imposible cambiar los valores de aquellos tipos. Puedes combinarlos y obtener nuevos valores a partir de ellos, pero cuando tomas un valor de string específico, ese valor siempre será el mismo. El texto dentro de él no puede ser cambiado. Si tienes un string que contiene `"gato"`, no es posible que otro código cambie un carácter en tu string para que deletree "rato".

## El diario del licántropo

```JS
let diario = []

function añadirEntrada(eventos, ardilla) {
    diario.push({ eventos, ardilla })
}
```

Ten en cuenta que el objeto agregado al diario se ve un poco extraño. En lugar de declarar propiedades como `eventos: eventos`, simplemente da un nombre de propiedad. Este es un atajo que representa lo mismo si el nombre de propiedad en la notación de llaves no es seguido por un valor, el valor se toma de la vinculación con el mismo nombre.

---

La **correlación** es una medida de dependencia entre variables estadísticas. Una variable estadística no es lo mismo que una variable de programación. En las estadísticas, normalmente tienes un conjunto de **medidas**, y cada variable se mide para cada medida. La correlación entre variables generalmente se expresa como un valor que varía de $-1$ a $1$. Una correlación de cero significa que las variables no están relacionadas. Una correlación de uno índica que las dos están perfectamente relacionadas -si conoces una, también conoces la otra. Uno negativo también significa que las variables están perfectamente relacionadas, pero que son opuestas- cuando una es verdadera, la otra es falsa.

Para calcular la medida de correlación entre dos variables booleanas, podemos usar el **coeficiente phi** ($\phi$). Esta es una fórmula cuya entrada es una tabla de frecuencias que contiene la cantidad de veces que las diferentes combinaciones de las variables fueron observadas. El resultado de la fórmula es un número entre $-1$ y $1$ que describe la correlación.

$$
\phi = \frac{ n_{ 11 } n_{ 00 } - n_{ 10 } n_{ 01 } }{ \sqrt{ n_{ 1\cdot } n_{ 0\cdot } n_{ \cdot 1 } n_{ \cdot 0 } } }
$$

## Ciclos de array

```JS
for (let entrada of DIARIO)
    console.log(`${entrada.eventos.length} eventos.`)
```

Cuando un ciclo `for` se vea de esta manera, con la palabra "of" ("de") después de una definición de variable, recorrerá los elementos del valor dado después `of`. Esto funciona no solo para arrays, sino también para strings y algunas otras estructuras de datos.

## Parámetros restantes

```JS
function maximo(...numeros) {
    let resultado = -Infinity

    for (let numero of numeros)
        if (numero > resultado)
            resultado = numero

    return resultado
}

console.log(maximo(4, 1, 9, -2)) // 9
```

---

```JS
let palabras = ["nunca", "entenderas"]

console.log(["tu", ...palabras, "completamente"]) // ["tu", "nunca", "entenderas", "completamente"]
```

## Objeto `Math`

Es usado como un contenedor que agrupa un grupo de funcionalidades relacionadas. Solo hay un objeto `Math`, y casi nunca es útil como un valor. Más bien, proporciona un **espacio de nombre** para que todas estas funciones y valores no tengan que ser vinculaciones globales.

Tener demasiadas vinculaciones globales "contamina" el espacio de nombres. Cuanto más nombres hayan sido tomados, es más probable que accidentalmente sobrescribas el valor de algunas vinculaciones existentes. Por ejemplo, no es poco probable que quieras nombrar algo "max" en alguno de tus programas. Dado que la función `max` ya incorporada en JavaScript está escondida dentro del Objeto `Math`, no tenemos que preocuparnos por sobrescribirla.

---

Aunque las computadoras son máquinas deterministas -siempre reaccionan de la misma manera dada la misma entrada- es posible hacer que produzcan números que parecen aleatorios. Para hacer eso, la máquina mantiene algún valor escondido, y cada vez que le pidas un nuevo número aleatorio, realiza cálculos complicados en este valor oculto para crear un nuevo valor. Esta almacena un nuevo valor y retorna un número derivado de él. De esta manera, puede producir números nuevos y difíciles de predecir de una manera que **parece** aleatoria.

## JSON

JavaScript nos da las funciones `JSON.stringify` y `JSON.parse` para convertir datos hacia y desde este formato. El primero toma un valor en JavaScript y retorna un string codificado en JSON. La segunda toma un string como ese y lo convierte al valor que este codifica.

```JS
let string = JSON.stringify(
    { ardilla: false, eventos: ["fin de semana"] }
)

console.log(string) // { "ardilla": false, "eventos": ["fin de semana"] }
console.log(JSON.parse(string).eventos) // ["fin de semana"]
```

## Resumen

Los objetos y arrays (que son un tipo específico de objeto) proporcionan formas de agrupar varios valores en un solo valor. Conceptualmente, esto nos permite poner un montón de cosas relacionadas en un bolso y correr alrededor con el bolso, en lugar de envolver nuestros brazos alrededor de todas las cosas individuales, tratando de aferrarnos a ellas por separado.
