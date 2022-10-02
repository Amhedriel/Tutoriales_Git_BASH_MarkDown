# Ignorar archivos y directorios con .gitignore

Ignorar archivos para que no sean subidos a nuestros repositorios de Git, esto se hace porque queremos tener archivos de configuración específicas para nuestra máquina por ejemplo variables de entorno, supongamos que trabajamos con una base de datos y esta base de datos nosotros la tendremos instalada en local.

En ese caso los usuarios, contraseñas y cualquier otro acceso sera diferente al de producción, asi que nosotros queremos tener ese archivo almacenado dentro de nuestra máquina y que este no se suba por error dentro de nuestro repositorio ya que no queremos que otras personas conozcan nuestra contraseña y ademas queremos que sea configurable de manera que la aplicación despliegue a produccion solamente una persona tenga acceso a esas variables de entorno, las cuales serviran para configurar la aplicación y que esta se conecte finalmente con la base de datos de producción.

## Colocar variables de configuracion

Abriremos Visual Studio Code y crearemos un nuevo archivo *.env* que es un nombre standar para variables de entorno, dentro de este archivo escribiremos por ejemplo: "password=123456 User=david" sopondremos que nuestra aplicacion se conectara a una base de datos MySql utilizando ambas variables.

Nos devolvemos a la terminal y escribimos `git status`

~~~ bash
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .env

nothing added to commit but untracked files present (use "git add" to track)
~~~

Veremos que aparece el archivo *.env* y no queremos que por algun error llegar a commitear este archivo, para eso, volveremos a Visual Studio Code y crearemos un nuevo archivo llamado *.gitignore* y dentro de este archivo debemos especificar cuales son los archivos o también cuales son las rutas  que queremos que Git ignore y que estas no vayan a mi repositorio; ignoraremos el archivo *.env* pero también podemos indicarle carpetas, por ejemplo: si estuvieramos trabajando con **NODE** podriamos indicar la carpeta *node_modules/* e ignoraria esta carpeta.

    $ vim .gitignore

    .env
    node_modules/

    :exit

Ahora revisemoslo con `git status`.

~~~bash
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)
~~~
observemos que ya no aparece el archivo *.env* pero en cambio *.gitignore* si, ahora agragaremos *gitignore*.

    $ git add .gitignore

Y lo comprometemos
~~~
$ git commit -m "agregando archivo gitignore"
[master 8398f44] agregando archivo gitignore
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore
~~~

## Tip

Hasta ahora esuvimos utilizando el comando de `git status` que nos muestra mucha mas información de la que necesitamos, por lo tanto otra alternativa que es maselegante y mas facil de seguir; nos devolvemos a nuestro editor de texto y vamos a empezar a realizar modificaciones.

Primero modificaremos *.gitignore* eliminando el **NODE**

    $ vim .gitignore

Segundo, agregamos contenido a *archivo1.txt* agregando un chanchito feliz más

    $ vim archivo1.txt
    chanchito feliz
    chanchito feliz

Tercero, creamos un *archivo1.txt* conteniendo un chanchito feliz.

    $ vim archivo2.txt

Por último regresamos al terminal y escribimos `git status`.

~~~Bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   .gitignore
        modified:   archivo1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        archivo2.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~
Ahora nos indica en que rama nos encontramos `On branch master`, los cambios que no se encuentran todavía en **stage** `Changes not staged for commit:`algunos cambios que todavía no se han agregado para que Git les pueda hacer seguimiento `Untracked files:` y también unos comandos de ejemplo que nosotros podemos utilizar `no changes added to commit (use "git add" and/or "git commit -a")` en caso que queramos realizar alguna determinada acción.

en este caso supondremos que nosotros ya sabemos todo, entonces ejecutaremos el siguiente comando `git status -s`

~~~Bash
$ git status -s
 M .gitignore
 M archivo1.txt
?? archivo2.txt
~~~
 Aparece todo esto; fijemonos que el primer archivo *M .gitignore* quiere decir que es un archivo que a sido modificado, si yo escribo `git add` y adiero mi archivo de `.gitignore` al ejecutar `git status` veremos que a cambiado de rojo a verde, indicando que este se ah agregado a la etapa de **stage** 
~~~
$ git add .gitignore
warning: in the working copy of '.gitignore', LF will be replaced by CRLF the
 next time Git touches it
~~~
~~~
$ git status -s
M  .gitignore
 M archivo1.txt
?? archivo2.txt
~~~

Ahora notamos que con *archivo2* tenemos 2 signos de interrogación que indican que este **archivo2** todavía no a sido agregado para Git le pueda hacer seguimiento. Agreguemos *archivo2*.

    $ git add archivo2.txt
~~~
$ git status -s
M  .gitignore
 M archivo1.txt
A  archivo2.txt
~~~
Veamos que ahora nos aparece una A al lado de *archivo2* esto quiere decir que nosotros estamos agregando este archivo.

Aprovechemos de agregar *archivo1*.

~~~
$ git add archivo1.txt
warning: in the working copy of 'archivo1.txt', LF will be replaced by CRLF the next time Git to
uches it
~~~
~~~
$ git status -s
M  .gitignore
M  archivo1.txt
A  archivo2.txt
~~~
Podemos ver que todos los archivos estan marcados con sus respectivas acciones y todas estan con el color verde lo que nos indica que todo esta listo para comprometer o commitear.

~~~
$ git commit -m "mostrando status corto"
[master 77e7967] mostrando status corto
 3 files changed, 4 insertions(+), 2 deletions(-)
 create mode 100644 archivo2.txt
~~~

Ahora veremos como podemos ver los cambios que hemos realizado, pero, de una manera un poco más visual. Agregaremos contenido a nuestro *archivo2* con chanchito triste y Felipe.

~~~Bash
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   archivo2.txt

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Vemos que nuestro *archivo2* esta listo para ser agreagado a nuestra etapa de **stage**, pero en lugar de eso nosotros utilizaremos el omando `git diff` y podremos ver todo el texto de lo que representarian los cambios que nosotros estamos dispuestos a agregar.

~~~Bash
$ git diff
warning: in the working copy of 'archivo2.txt', LF will be replaced by CRLF the next time Git to
uches it
diff --git a/archivo2.txt b/archivo2.txt
index 22fb799..8a626aa 100644
--- a/archivo2.txt
+++ b/archivo2.txt
@@ -1 +1,3 @@
-anchito feliz
+Chanchito feliz
+chanchito triste
+Felipe
~~~
Podemos ver las diferencias de archivo2.txt, nos indica que se elimino la línea de *anchito feliz* y se agrego una nueva de *Chanchito feliz, chanchito triste, Felipe*.
Porque nos indica que la pimera linea la elimino y luego la volvió a agregar?, lo que pasa es que nosotros solo teníamos la línea de *anchito feliz* y no habríamos apretado enter, no existía un salto de línea, entonces agregamos el salto de línea y ese salto de línea se agrega sobre la misma línea que en este caso sería *anchito feliz*, entonces eliminara la primera línea y agregará la misma línea pero con un caracter de salto de línea y despues agregara lo demás.

`@@ -1 +1,3 @@` esto nos indica que está comenzando desde la línea 1, con la versión anterior de nuestro archivo y después tendríamos la siguiente versión *+1,3* que serían los cambios que nosotros realizamos comenzando desde la línea 1 y que ah extraido 3 líneas las cuales vendrían siendo nuestros cambios.

Para poder salir de esa pantalla debemos apretar la tecla q (quit).

Ahora si agreguemos estos cambios.

~~~~
$ git add archivo2.txt
warning: in the working copy of 'archivo2.txt', LF will be replaced by CRLF the next time Git to
uches it
~~~~
Ahora veremos `git diff` nuevamente

    $ git diff

Ahora notamos que no tenemos absolutamente ningún cambio.

Utilizaremos una versión de `diff` diferente agregando la opción de `--staged` para poder ver los cambios que se encuentran en la etapa de **stage**.

~~~Bash
$ git diff --staged
diff --git a/archivo2.txt b/archivo2.txt
index 22fb799..8a626aa 100644
--- a/archivo2.txt
+++ b/archivo2.txt
@@ -1 +1,3 @@
-anchito feliz
+Chanchito feliz
+chanchito triste
+Felipe
~~~

Por ende, la primera versión del comando cuando es solamente `git diff`, nos va a mostrar todos los cambios que nosotros hemos escrito pero que todavía no hemos pasado a la etapa de **stage**, si agregamos `--staged` nos va a mostrar todos los cambios que se encuentran en nuestra etapa de **stage** aparecera acá, así podremos ver los cambios que queremos comprometer y no queremos ver absolutamente todo.

[Siguiente **&#129042;**](010_Revisar_Historial.md "Git log")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")

