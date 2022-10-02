# Agregando cambios a stage
Abrirenos nuestro nuestro editor de texto desde el Bash de Git, para realizar modificaciones a nuestro proyecto y asi empezar a trabajar con Git, utulizaremos el comando: `code .`, el punto quiere decir: *"quiero que habras la carpeta donde yo me encuentro"*.

Entonces abrira Visual Studio Code en la carpeta de ejemplo: miweb, ahora agrgaremos un archivo llamado, `archivo1.txt` y escribiremos `chanchito feliz`.

Una vez guardado y de regreso a Bash escribiremos el comando: `git status` lo que hace es mostrarnos el estado actual de nuestro repositorio.

Inicializamos un repositorio como si fuese un proyecto que gestionaremos con Git:

~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb
$ git init

Initialized empty Git repository in C:/Users/David/Dropbox/VisualStudioCode/miweb/.git/
~~~

Ahora veremos el estado actual de nuestro repositorio:
~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        archivo1.txt

nothing added to commit but untracked files present (use "git add" to track)
~~~

Revisando la información veremos que `No commits yet` nos esta indicando que todavía no existe ningún **commit** y que también se encuentra `Untracked files:` lo que significa que son archivos que Git no está siguiendo, por defecto Git no sigue todos los archivos que nosostros coloquemos dentro de nuestro proyecto, para seleccionarlos debemos utilizar el comando `git add` con el nombre del archivo.

    $ git add archivo1.txt
Oh podemos colocar alguna expresión regular:

    $ git add *.txt

Que agregará todos los archivos que tengan la extension txt.

O podemos colocar un punto:

    $ git add .
Lo que agregará todos los archivos que aparezcan dentro de este listado o todos los que al colocar `git status` aparezcan en rojo, sin embargo se considera una ***mala práctica***, porque podríamos incluir archivos modificados que no queriamos reemplazar o se ppodrian encontrar archivos binarios muy grande como imagenes, videos, ejecutables, etc.

Agregaremos el archivo del modo tradicional:

    $ git add archivo1.txt

Ahora veremos el resultado con el comando de `git status`
~~~ Bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   archivo1.txt
~~~
Ahora veremos que nos esta indicando que seguimos en la rama de Main `On branch master`.
Que no tenemos ningún *commit* `No commits yet`.

Y también que se encuentran cambios listos para ser comprometidos `Changes to be committed:`

Los archivos que se encuentren de color verde son archivos que se encuentran en una etapa de ***stage***, pero aun no lo vamos a comprometer, por ahora crearemos otro archivo.

Ahora agregaremos otro archivo2.txt con el texto de chanchito triste.

Regresamos a la terminal y utilizamos `git status`.
~~~Bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   archivo1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        archivo2.txt
~~~
Nos muestra nuestro archivo1.txt que se encuentra en la etapa de **stage**, sin embargo el archivo2.txt todavía no esta siendo seguido por Git, asi que lo agregaremos con `git add`.
~~~
$ git add archivo2.txt
~~~

Es posible agregar mas de un archivo a la vez con un espacio entre los archivos.

    $ git add archivo1.txt archivo2.txt

Ahora revisaremos que es lo que nos esta mostrando.

~~~bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   archivo1.txt
        new file:   archivo2.txt
~~~

Ahora podemos ver que se encuentran 2 archivos agregados a nuestra etapa de **stage** veremos ahora que es lo que ocurre si realizamos una modificación en archivo2.txt por ejemplo. Modificando el texto de "chanchito triste" a "chanchito feliz"

~~~
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   archivo1.txt
        new file:   archivo2.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   archivo2.txt
~~~

Esto nos indica que en la etapa de **stage** son los cambios cuando archivo2 contenía el texto de "chanchito triste", por ende si nosotros comprometemos esto se va a comprometer que archivo2 tiene el texto de "chanchito triste", si nosotros queremos reemplazar este cambio tenemos que volver a agreagar archivo2.

~~~
$ git add archivo2.txt
warning: in the working copy of 'archivo2.txt', LF will be replaced by CRLF the next time Git touches it
~~~   
De nuevo utilizamos `git status`
~~~Bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   archivo1.txt
        new file:   archivo2.txt
~~~

Y podemos ver el estado completo de nuestra etapa de **stage** de esta manera nosotros poder tomar archivos a los cuales les hemos realizado cambios y pasarlos a una etapa de **stage**, lo que estamos pasando a la etapa de **stage** no son los archivos mismos, lo que son las modificaciones que realizamos sobre estos archivos.

Ahora da la coincidencia de que hemos creado un nuevo archivo con cambios, pero una vez comprometamos esto veremos que al realizar un cambio vamos a poder seguir agregando cambios a esta etapa de **stage**, no el archivo, si no los cambios.

En este momento ya estamos listos para comprometer **(commit)** nuestro trabajo existen principalmente 2 formas.

La *primera* y recomendada es utilizando el comando de `git commit -m ""`dentro de las comillas dobles se debe colocar un mensaje que tenga sentido, en este caso es un **commit** inicial y esto solamente por este curso colocaremos "commit inicial"

~~~bash
$ git commit -m "Commit inicial"
[master (root-commit) 1e1c196] Commit inicial
 2 files changed, 3 insertions(+)
 create mode 100644 archivo1.txt
 create mode 100644 archivo2.txt
~~~
Ahora nuestros cambios han sido comprometidos, fueron commiteados `commit`.

Cuando no se coloca ningún mensaje aparecera una ventana de advertencia, ya sea en Vim o en Code, si fue abierto en vim deberemos presionar ESC I para poder editar o la tecla INSERT.
~~~vim

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Changes to be committed:
#	modified:   historia.txt
#
~~~
Así en la parte de arriba del mensaje podremos dejar escrito el mensaje (obligatorio) del cambio que se hizo y deberemos saber que el texto escrito con los # serán invisibles.

~~~vim
Commit inicial
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Changes to be committed:
#	modified:   historia.txt
#
~~~
En caso de abrir con Vim para salir debemos presionar ESC + SHIFT Z Z.

Revisaremos lo realizado con `git status`
~~~
$ git status
On branch master
nothing to commit, working tree clean
~~~
Seguimos en nuestra rama de main, pero no se encuentra absolutamente nada dis ponible para poder hacer un commit

La *segunda* forma despues de hacer un cambio en alguno de nuestros archivos seria:

    $ git commit

Esto nos devolvería a nuestro editor de código y tendriamos que escribir un mensaje que tenga sentido en la primera línea.
 ~~~
 $ git status
On branch master
nothing to commit, working tree clean
 ~~~
Y ya estaría realizado el **commit**.

---
## Eliminar Archivos

En este momento eliminaremos archivo2.txt con el comando `rm`.

    $ rm archivo2.txt
Revisaremos el estado actual
~~~bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    archivo2.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Veremos que ahora nos aparece el texto `deleted:   archivo2.txt`, esto significa que son cambios que realizamos que no se encuentran en la etapa de **stage**.

Agregaremos este cambio a **stage**

    $ git add archivo2.txt

Ahora veremos que con `git status` veremos que es lo que esta ocurriendo.

~~~bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    archivo2.txt

~~~
Ahora nos esta mostrando que tenemos la opcion de eliminar el archivo2.txt y que esta se encuentra dentro de nuestra etapa de **stage**.

Lo que haremos ahora será realizar un **commit** de este cambio.

~~~bash
$ git commit -m "Eliminando archivo 2"
[master 1465ffd] Eliminando archivo 2
 1 file changed, 2 deletions(-)
 delete mode 100644 archivo2.txt
~~~
Veremos que nuestro cambio a sido comprometido.

~~~
$ git status
On branch master
nothing to commit, working tree clean
~~~

El archivo ya no se encuentra listado en nuestra etapa de **stage**

Este paso de eliminar el archivo y luego agregarlo a **stage** es algo repetitivo afortunadamente Git tiene un comando que nos ahorrara un paso.

    $ git rm archivo1.txt
    rm 'archivo1.txt'
Revisamos.
~~~bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    archivo1.txt

~~~

Podemos ver que el archivo1.txt se escuentra inmediatamente disponible y listo para ser commiteado o comprometido, si nosotros quisieramos sacar algún cambio que nosotros hayamos pasado a la etapa de **stage** Para eso podemos usar el comando que nos esta indicando `"git restore --staged <file>..."`.

    $ git restore --staged archivo1.txt

~~~bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    archivo1.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Ahora nuestro archivo ya no se encuentra en nuestra etapa de **stage**.

---
## Recuperar Archivos eliminados

Que pasaria si quisiera descartar los cambios, recuperar el archivo.

Podemos utilizar el comando `git restore`.

    $ git restore archivo1.txt

~~~bash
$ git status
On branch master
nothing to commit, working tree clean
~~~

Vemos que todos los cambios se encuentran completamente limpios.

Revisamos con `ls`
~~~
$ ls
archivo1.txt
~~~
Y el archivo a sido restaurado correctamente.

---

## Mover archivo o cambiar el nombre

De momento el único archivo que tenemos es archivo1.txt y lo modificaremos al ser nuestro único archivo.

Escribiremos el comando `mv` que es el comando para mover archivos y le tenemos que indicar cual es el origen y con un espacio elegir el destino.

    $ mv archivo1.txt archivo.txt
~~~
$ ls
archivo.txt
~~~

Ahora veremos el status.
~~~bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    archivo1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        archivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Esto nos muestra que tenemos 2 cambios, primero fue el de eliminar archivo1.txt y el segundo es que se ha creado un nuevo archivo, que en este caso se llama archivo.txt el cual Git no lo está siguiendo.

Entonces agregaremos archivo1 y archivo.

    $ git add archivo1.txt archivo.txt
~~~bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    archivo1.txt -> archivo.txt
~~~
Veremos ahora que nos aparece la acción de "rename" indicando que el archivo1.txt a cambiado de nombre a archivo.txt.

Ahora si podemos comprometer nuestros cambios.

~~~bash
$ git commit -m "Renombrando archivo"
[master 3a8c2cf] Renombrando archivo
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename archivo1.txt => archivo.txt (100%)
~~~
Por suùesto que Git viene con una herramienta para que nosotros podamos renombrar y agregar inmediatamente a **stagend** nuestros cambios, en este caso el comando es de `git mv` y debemos indicar el nombre del archivo

    $ git mv archivo.txt archivo1.txt

~~~bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    archivo.txt -> archivo1.txt
~~~
Veremos ahora que este cambio a sido agreagado inmediatamente a **stage**.

Ahora lo commitearemos.
~~~
$ git commit -m "Devolviendo el nombre al archivo"
[master f1060d5] Devolviendo el nombre al archivo
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename archivo.txt => archivo1.txt (100%)
~~~

[Siguiente **&#129042;**](009_Ignorar_Archivos_y_Directorios.md "Ignorar archivos y directorios con .gitignore")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")


