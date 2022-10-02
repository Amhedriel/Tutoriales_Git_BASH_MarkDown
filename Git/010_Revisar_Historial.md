# Git log
Ahora veremos todo el historial de nuestro repositorio.
Existe un comando llamado `git log` al ejecutarlo veremos mucha información, ver a la persona que realizó cierto **commit** al igual que el correo y también un mensaje del **commit**, para navegar en esta pantalla es posible con la barra de espacio, sin embargo existe otra mas cómoda `git log --oneline`.

~~~Bash
$ git log --oneline
77e7967 (HEAD -> master) mostrando status corto
8398f44 agregando archivo gitignore
f1060d5 Devolviendo el nombre al archivo
3a8c2cf Renombrando archivo
1465ffd Eliminando archivo 2
1e1c196 Commit inicial
~~~
Mostrará el historial con un pequeño hash, el cual sirve como un identificador de ese **commit** sería un número único con el cual se va a identificar ese commit dentro de nuestro registro en Git, además de eso nos colocara el mensaje que nosotros colocamos dentro de nuestro **commit** por eso los nombres que colocamos dentro de nuestro **commit** sean algo que tenga sentido no solo para nosotros si no también para otros desarrolladores.
Para salir de la pantalla puedes presionar `q`.

## Ver del commit

Revisemos el historial con `git log historia.txt`

~~~bash
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
~~~
## Diferencias en un archivo

Si queremos ver las diferencias de un archivo podemos utilizar `git diff bb99c03c1fea9c949c8e314e1636fbc8f2316cc7` y digamos que lo queremos comparar con la primera versión, enton agregamos un espacio y copiamos `112e816e9d3936c441e7f0174699a3fa55885ac3`

~~~Bash
$ git diff bb99c03c1fea9c949c8e314e1636fbc8f2316cc7 112e816e9d3936c441e7f0174699a3fa55885ac3
diff --git a/historia.txt b/historia.txt
index 9121bd2..9bffa93 100644
--- a/historia.txt
+++ b/historia.txt
@@ -1,9 +1,5 @@
 Esta es la historia de Freddy Vega

-Freddy Vega tiene 33 años y nació en Colombia
+Freddy Vega tiene 32 años y nació en Colombia

 Hoy hablaremos de su historia.
-
-En cámara parece alto pero la verdad no es tan alto.
-
-Hoy es el CEO de Platzi.
~~~
---
## Git show

Con este comando nosotros podemos ver los cambios que hicimos en nuestro archivo

~~~
$ git show
commit bb99c03c1fea9c949c8e314e1636fbc8f2316cc7 (HEAD -> master)
Author: David Amhed Beltrán Rubín de Celis <davikin_01@hotmail.com>
Date:   Sun Aug 21 11:37:27 2022 -0300

    Agregamos el cargo de la persona

    La persona es Freddy

diff --git a/historia.txt b/historia.txt
index 68f3347..9121bd2 100644
--- a/historia.txt
+++ b/historia.txt
@@ -5,3 +5,5 @@ Freddy Vega tiene 33 años y nació en Colombia
 Hoy hablaremos de su historia.

 En cámara parece alto pero la verdad no es tan alto.
+
+Hoy es el CEO de Platzi.
~~~

[Siguiente **&#129042;**](011_Ramas_Branch.md "Branch o ramas en Git")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")

