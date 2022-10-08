# Branch o ramas en Git

Hasta el momento estuvimos trabajando de un forma lineal, modificando los archivos en la rama principal, pero si nosotros eestuvieramos trabajando en una gran aplicacion y actualizando partes, agregando funionalidades o corrigiendo errores entonces tendríamos que trabajar con una rama, que se separa de la línea principal y nos permite desarrollarla para después subirla de nuevo solicitando un **mech** a la línea principal o rama **branch** principal.

Lo primero que haremos será revisar el status `git status`.

~~~Bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   archivo2.txt
~~~

Y luego vamos a restaurar este archivo

    $ git restore --staged archivo2.txt

Ejecutemos `git status`.

~~~Bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   archivo2.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Y descartaremos estos cambios.

    $ git restore archivo2.txt

Ahora revisaremos que estamos en un **branch** limpio
~~~
$ git status
On branch master
nothing to commit, working tree clean
~~~

---
## Crear Rama (**branch**)

Antes de crear una rama verificaremos en que lugar nos esncontramos para eso `git branch`

~~~
$ git branch
* master
~~~

Aquí vemos que nos esta indicando el texto de ***\* master*** (main) eso indica que la rama en la que estamos es la principal y será en la que trabajemos. Para crear una rama tenemos que escribir el comando `git checkout -b ` seguido de el nombre de la rama (Hay algunas empresas que prefieren utilizar la nomenclatura de `features/nombre-de-la-funcionalidad`, pero otras prefieren colocar el número del ticket que ellos quieren arreglar `SS-4525-AE`) en nuestro caso sencillamente usaremos `ramab`.

~~~
$ git checkout -b ramab
Switched to a new branch 'ramab'
~~~

Nos indica que nos estamos cambiando a una rama que se llama **ramab**, ahora escribimos `git branch`

~~~
$ git branch
  master
* ramab
~~~
Observemos que existe **brach** main o master pero también existe la rama que se llama ramab.
Ahora podemos realizar cambios sobre nuestros archivos.

Volvamos al editor de texto y modifiquemos *archivo2.txt* con un chanchito feliz extra y un espacio vacio.

    $ vi archivo2.txt

Ahora lo agregamos.

    $ git add archivo2.txt

Y haremos un **commit**

~~~Bash
$ git commit -m "actualizando archivo 2"
[ramab 7417435] actualizando archivo 2
 1 file changed, 3 insertions(+), 1 deletion(-)
~~~

## Revisar **historial**

Ahora revisemos el historial en el cual nosotros nos encontramos trabajando `git log --oneline`

~~~Bash
$ git log --oneline
7417435 (HEAD -> ramab) actualizando archivo 2
77e7967 (master) mostrando status corto
8398f44 agregando archivo gitignore
f1060d5 Devolviendo el nombre al archivo
3a8c2cf Renombrando archivo
1465ffd Eliminando archivo 2
1e1c196 Commit inicial
~~~

Aqui podemos ver que nos encontramos en la cabeza (HEAD) de la (BRANCH) ramab y yo me encuentro al final justamente con la parte de ramab, el último código que se a escrito.
Y también se encuentra una rama que se llama *master* y en este caso la cabeza de master esta diciendo que es el del commit mostrando *status corto*.

El siguiente comando `cat archivo2.txt` que nos mostrará el contenido de nuestro *archivo*.

~~~Bash
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (ramab)
$ cat archivo2.txt
Chanchito feliz
chanchito feliz
~~~

## Cambio de rama (branch) y merge

Fijemonos que sucede si nos cambiamos de **rama** a la rama master.

~~~bash
$ git checkout master
Switched to branch 'master'
~~~
Veamos el contenido de ***master***.

~~~bash
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (master)
$ cat archivo2.txt
Chanchito feliz
~~~
De esta manera nosotros podemos tener varias versiones de código que están siendo trabajadas, nosotros tendremos *ramab* donde ya habíamos agregado una nueva línea, pero en la **rama** master nosotros vemos reflejado que aún no están los cambios.

Ahora para poder traernos los cambios de la **rama**b a la ***rama master*** tenemos que escibir en la ***rama master*** con el comando `git merge` seguido del nombre de la **rama** que se quiere traer, en este caso `ramab`

~~~bash
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (master)
$ git merge ramab
Updating 77e7967..7417435
Fast-forward
 archivo2.txt | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)
~~~

Aqui podemos ver como se trajo el **archivo2.txt** con sus cambios incluidos, y si ahora realizamos un:

~~~
$ cat archivo2.txt
Chanchito feliz
chanchito feliz
~~~
Vamos a ver los cambios de Chanchitos felices.

Asi es que cada trabajador se crea su rama implementa la funcionalidad y luego la mezcla o hace un **merch** con la **rama** de master.

[Siguiente **&#129042;**](011.1_Crear_Ramas.md "Crear una Rama Nueva")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")
