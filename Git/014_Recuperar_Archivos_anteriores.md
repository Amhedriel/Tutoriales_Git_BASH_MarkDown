# Recuperar archivos anteriores

Que pasa cuando quieres traer un cambio que esta en staging pero no en el repositoriopero que no esta en tu carpeta, por ejemplo: si un miembro del equipo hizo un cambio al archivo que no tenemos en los archivos locales pero debemos trabajar sobre el mismo archivo debemos ir a la rama final del repositorio y para traer a nuestra carpeta existe un comando llamado `chekout` con este comando podemos traer los ultimos cambios o los cambios que necesitemos, no necesariamente los recientes, si no los que podrian ser un poco antes hacia la carpeta, podemos traer todos los cambios, solo ciertos cambios o los cambios de ciertos archivos dependiendo de como modifiquemos el comando `chekout`.

Recordemos que cada **commit** es una nueva versión de nuestro archivo, V1, V2, V3... hacia nuestro repositorio, para lanzar una versión experimental, desarrollar una rama y luego unirlka a la master si estamos conformes con el resultado esperado.

---
## Volver a una versión anterior

Con `git reset` mas el ide de los cambios que hayamos realizado podemos volver a esa versión anterior, si agregamos `--hard` todo vuelve a una versión anterior, pero si utilizamos `--soft` sigue en **staging** y podemos revisarlo para volver a la versión anterior.

~~~Bash
$ git log historia.txt
commit bb99c03c1fea9c949c8e314e1636fbc8f2316cc7 (HEAD -> master)
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sun Aug 21 11:37:27 2022 -0300

    Agregamos el cargo de la persona

    La persona es Freddy

commit f28d9f7451772d2c0fd2093be02d2dacf1ca18de
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sun Aug 21 10:03:32 2022 -0300

    Agregamos un cambio a su estatura

commit 112e816e9d3936c441e7f0174699a3fa55885ac3
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sat Aug 20 20:56:11 2022 -0300

    Este es el primer commit de este archivo

David@Ciri MINGW64 ~/Git/proyecto1 (master)
~~~

Volveremos atras con la opción `--hard`

~~~
$ git reset f28d9f7451772d2c0fd2093be02d2dacf1ca18de --hard
HEAD is now at f28d9f7 Agregamos un cambio a su estatura
~~~

Ahora nos indica que nuestro "head" (master) es ahora f28d9f7 (ID)
en donde agregamos un cambio a su estatura

~~~
Esta es la historia de Freddy Vega

Freddy Vega tiene 33 años y nació en Colombia

Hoy hablaremos de su historia.

En cámara parece alto pero la verdad no es tan alto.
~~~

Perdiendo así los datos de su posicion actual en la empresa.

Ahora viendo con `git log`, es como si todo lo anterior hubiera desaparecido completamente, tener cuidado porque esto realmente borra todo lo que hicimos antes, es una forma de volver en el historial de una manera muy agresiva.

~~~
$ git log
commit f28d9f7451772d2c0fd2093be02d2dacf1ca18de (HEAD -> master)
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sun Aug 21 10:03:32 2022 -0300

    Agregamos un cambio a su estatura

commit 112e816e9d3936c441e7f0174699a3fa55885ac3
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sat Aug 20 20:56:11 2022 -0300

    Este es el primer commit de este archivo
~~~

---

## Recuperar el master

Si lo que nosotros queremos es recupera la ultima version commiteada en la master entonces deme colocar `git checkout master` seguido del archivo que queremos arreglar, modificar, traer de vuelta con un espacio

    $ git checkout master historia.txt
    Updated 1 path from 6ab4581

