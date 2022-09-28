# Guía Markdown

## Encabezados
<!-- Una almohadilla generará encabezado tipo h1, con 2 tipo 2 con 3 tipo 3... hasta 6 -->
# Encabezado 1
## Encabezado 2
### Encabezado 3
#### Encabezado 4
##### Encabezado 5
###### Encabezado 6

---
## Párrafos y saltos de línea

<!-- Para generar un nuevo párrafo separa el texto con una línea en blanco (Pulsando dos veces intro).
Útil para realizar un salto de línea y empezar una frase en una línea siquiente dentro del mismo párrafo -->
"Andando con sus patitas mojadas,

el gorrión

por la terraza de madera"

---
## Citas

>Esto es una cita

>Continuación de la cita

---
## Listas

### Desordenadas
- Elemento 1
* Elemento 2
+ Elemento 3

### Numeradas
1. Elemento 1
2. Elemento 2
3. Elemento 3
    - Elemento 4

<!-- como se vio en el ejemplo de numeradas se pueden anidar ambos tipos de listas -->

---

## Separaciones
<!-- mediante markdown intercambiara estos símbolos por la etiqueta <hr> 3 guiones, 3 barras bajas o 3 asteriscos -->
Esto es separación

***
---
___

## Negritas y Cursivas
<!-- Markdown admite las maneras de crear estos estilos, mediante asteriscos o guiones bajos, se recomienda usar siempre asteriscos -->
<!-- Si rodeas una palabra o frase con tan solo uno de estos elementos aplicaras una cursiva en cuestión -->
*No sé si tengo tiempo. Quizás me dé pronto por vencido y en lugar de eso me eche una siesta. ¡Hoy es 12 de Agoato y es mi cumpleaños! Una vez quise ser astrofísico. Todo el mundo debe aprender por sí mismo al final.*

<!-- Si utilizas 2 se aplicara la negrita o resaltado-->
**No sé si tengo tiempo. Quizás me dé pronto por vencido y en lugar de eso me eche una siesta. ¡Hoy es 12 de Agoato y es mi cumpleaños! Una vez quise ser astrofísico. Todo el mundo debe aprender por sí mismo al final.**

<!-- Si aplicas 3 serán negritas o resaltadas y Cursivas a la vez -->
***No sé si tengo tiempo. Quizás me dé pronto por vencido y en lugar de eso me eche una siesta. ¡Hoy es 12 de Agoato y es mi cumpleaños! Una vez quise ser astrofísico. Todo el mundo debe aprender por sí mismo al final.***

---

## Enlaces
<!-- Para crear enlaces debemos encerrar en corchetes la palabra frase que quieras utilizar como texto ancla y seguido sin espacios encerrar entre paréntesis el enlace en cuestión-->
[Enfoque Nómada](https://enfoquenomada.com)

<!-- Se puede añadir información extra entrecomillada justo después del enlace, para que esto sea el Title del enlace -->
[Enfoque Nómada](https://enfoquenomada.com "Productividad Móvil")

<!-- Si quieres que el URL sea el mismo enlace basta conque incluyas la propia URL entre los símbolos <> -->
<https://enfoquenomada.com>

---

## Imágenes
<!-- Las imagenes se añaden de una forma similar a los enlaces en este caso se encierra el texto alternativo entre corchetes y entre paréntecis la ruta a la imágen, pero para que funcione como código para insertar imágenes se debe insertar un símbolo de exclamación al principio del mismo -->
![Ebook navegador minimalista](https://enfoquenomada.com/wp-content/uploads/2016/07/Crear-navegador-minimalista.jpg)

<!-- También es posible cargar la imagen localmente guardando la imagen en la misma carpeta del proyecto de Mardown -->

![Logo de Visual Studio Code](VisualStudioCodeLogo1.png)

---

## Código
<!-- Para la documentación técnica, puedes incluir cajetines de código de cualquier lenguaje, para que este no sea interpretado y se muestre de manera limpia -->
<!-- si sólo será una línea de código basta conque inicies con 4 espacios en blanco-->

    Esto es código

<!--Pero si generarás más codigo, se encerrarán con 3 Virgulillas (alt Gr + 4)~~~ por arriba y por debajo -->
~~~
Eso es porque no quieres estar solo. No puedo vivir así. Supongo que es diferente cuando lo consideras a largo plazo.
~~~
<!-- Si solo quieres resaltar código dentro de una frase se lo debe incluir entre 2 acentos graves `` -->

También puedes usar `código` así.

<!-- Ahora bien, si quiero resaltar el código con colores debo indicar de que lenguaje se trata -->

```javascript
const mongoose = require('moongose');

moongose.set('useFindAndModify', false);
moongose.connect('mongodb://localhost/node-notes-db', {
    useCreateIndex: true,
    useNewUrlParser: true
})
    .then(db => console.log('DB is connected'))
    .catch(err => console.error(err));
```
```html
<h1>Hello World</h1>
 ```
___

## Anular Markdown
<!-- Markdown utilita símbolos comunes para marcar el texto de una manera muy rápida, para poder utilizar estos símbolos deberas usar una barra invertida \ -->
De esta forma anulas \*Markdown*.

---

## Generar tablas

<!-- También podemos generar tablas (Celdas y Columnas) ahora si quieres que esten alineadas al medio debes colocar 2 puntos al principio y al final de los guiones y si se prefiere alinearlos a mano izquierda-->

| TABLES    | ARE           | COOL  |
| ----------|:-------------:|------:|
| col 3 is  | rigth-aligned | $1600 |
| col 2 is  | centered      |   $12 |
| zebra stripes| are neat   |    $1 |

---
