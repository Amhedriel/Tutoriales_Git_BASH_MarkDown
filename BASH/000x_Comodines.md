# Comodines

Por lo general yo me refiero a los comodines caracteres que pueden tener cualquier valor o son utiles para cierto funcionamiento en Bash.

Como un ejemplo muy común es utilizar el asterisco *\** que básicamente funciona para referirnos a cualquier cantidad de caracteres, podríamos ejemplificarlo así:

    $ cp *.txt /Carpeta1

Lo que resulta en copiar todos los archivos con extensión *.txt* de la carpeta actual se copien en la *carpeta1*. Con esto estaríamos ahorrando bastante tiempo en lugar de copiar archivo por archivo indicando el nombre con su extensión.

## *\**

Como lo vimos más arriba es un comodin, al menos para mí, muy importante para poder agilizar nuestras acciones.

Otro ejemplo que podemos dar:

    $ cp libro1.* /Carpeta1

Supogamos que tenemos varios libros de texto con diferentes formatos, y queremos copiar uno de estos para imprimir en alguna imprenta de la zona, pero no estamos seguros que tipo de formato nos es más conveniente para imprimir sin tener que arriesgarnos a fallas de impresión, tenemos todos en una carpeta muy desordena y los archivos están guardados con libro + numeración por comodidad, y tenemos el archivo *libro1* en varios formatos pero con el mismo nombre, lo que haremos es indicar que queremos copiar todos los *libro1* con todos los formatos que tenemos como .doc, .pdf, .txt, etc. entonces usaremos el comodín *.\** en donde \* simboliza que todos los formatos sin importar la longitud serán copiados.

Y en caso de querer copiar todo pues...

    $ cp *.* /Carpeta1

Pero se puede combinar con varias opciones:

    $ cp libro*.txt /Carpeta1

Copiara todos los archivos .txt donde su nombre empieza con los caracteres libro, ya que el \* agreagará los caracteres faltantes, com podrían ser: libro*s*, libro*1*, libro*2*, libro*DeContabilidad*, libro*AprendeAProgramar*, y asi...

    $ cp *libro*.txt /Carpeta1

Copiaremos todos los archivos que tengan los caracteres libro en ese orden en cualquier lugar de su nombre y tengan la extensión .txt, podrían ser: Mis_*libro*s_queridos, Un_*libro*_para_recordar, Listas y recopilaciones de los *libro*s más vendidos en el siglo XX.txt.

Y el comodín \* se puede usar en muchas cosas más no solo con el comando de `cp`.

---
## ?

Se diría que funciona como el \* pero que solo reemplaza un caracter con cualquiera que pueda ser:

    $ cp libro?.txt /Carpeta1

Con este comando estamos copiando todos los archivos .txt que empiecen con *libro* y el siguiente caracteer sea cualquiera: libro**1**, libro**2**, libro**s**, libro**A**, ...

Mientras más *?* coloquemos, más caracteres se reemplazarán, también sirve en las extensiones, etc.



