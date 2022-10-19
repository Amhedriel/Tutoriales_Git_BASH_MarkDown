# Para borrar archivos rm (Resumen)

Para borrar archivos podemos utilizar el comando `rm` seguido por un espacio el o los nombres separados por espacios de el/los archivos que queramos eliminar.

Est5e comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos "viajar en el tiempo" y recuperar el último **commit** antes de vorrar el archivo en cuestión.

Recuerda que `git rm` no puede usarse sin más. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

`git rm --cached` Elimina los archivos de nuestro repositorio local y del área de **staging**, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de **trackear** el historial de los cambios de estos archivos, por lo que pasaran a un estado *untracked*.

`git rm --force` Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podemos recuperarlos si es necesario (pero debemos usar comando más avanzados)

## Git reset

Este comando nos ayuda a volver en el tiempo en el historial, pero no como `git checkout` que nos deja ir, mirar, pasear y volver. Con `git reset` volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir, no hay vuelta atrás.

`git reset --soft` Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en **staging**, así podemos aplicar las últimas actualizaciones a un nuevo **commit**.

`git reset --hard` Borra todo, absolutamente todo, toda la información de los **commits** y del área de **staging** se borra el historial.

`git reset HEAD` Este es el comando para sacar archivos del área de **staging**. No para borarrlos, solo para que los últimos cambios de estos archivos no se envíen al último **commit**, a menos que cambiemos de opinión y los incluyamos de nuevo en **staging** con `git`.

## Borrar directorios RMDIR

Lo mismo que en el caso anterior pero con directorios `rmdir`.

---
## NOMBRE
git-rm - Elimina archivos del árbol de trabajo y del índice.

### Sinopsis

~~~bash
git rm [-f | --force] [-n] [-r] [--cached] [--ignore-unmatch]
          [--quiet] [--pathspec-from-file=<file> [--pathspec-file-nul]]
          [--] [<pathspec>…​]
~~~

Quite los archivos que coincidan con pathspec desde el índice, del árbol de trabajo y del índice.
`git rm` no eliminará un archivo solo de su directorio de trabajo. (No hay ninguna opción para eliminar un archivo solo del árbol de trabajo y mantenerlo en el índice; use `/bin/rm` Si usted quiere hacer eso).
Cuando `--cached` es proporcionado, el contenido `staged` debe coincidir con la punta de la rama o el archivo en el disco, lo que permite que el archivo se elimine solo del índice.

## Eliminación de archivos que han desaparecido del sistena de archivos

No hay ninguna opción de `git rm` para eliminar del índice sólo las rutas que han desaparecido del sistema de archivos. Sin embargo, dependiendo del caso de uso, hay varias formas que se pueden hacer.
### Usando "git commit -a"

Si tiene la intención de que su próximo *commit* registre todas las modificaciones de los archivos *trackeados* en el árbol de trabajo y registre todas las eliminaciones de archivos que se han eliminado del árbol de trabajo con `rm` (en lugar de `git rm`), use `git commit -a`, ya que automáticamente notará y registrará todas las eliminaciones. También puede tener un efecto similar sin *commitear* mediante el uso de `git add -u`.
### Usando "git add -A"

Al aceptar una nueva colocación de código para una *rama* de proveedor, es probable que desee registrar tanto la eliminación de rutas de acceso y las adiciones de nuevas rutas, como las modificaciones de rutas existentes.

Normalmente, primero eliminaría todos los archivos rastreados del árbol de trabajo usando este comando:

    git ls-files -z | xargs -0 rm -f

Y, a continuación, descomprima el nuevo código en el árbol de trabajo. Alternativamente, puede *rsync* los cambios en el árbol de trabajo.

Después de eso, la forma más fácil de registrar todas las eliminaciones, adiciones y modificaciones en el árbol de trabajo es:

    git add -A

### Otras maneras

Si todo lo que realmente desea hacer es eliminar del índice los archivos que ya no están presentes en el árbol de trabajo (tal vez porque su árbol de trabajo está sucio, por lo que no puede usar `git commit -a`), use el siguiente comando:

    git diff --name-only --diff-filter=D -z | xargs -0 git rm --cached


## SUBMÓDULOS

Solo los submódulos que usan un gitfile (lo que significa que fueron clonados con una versión de Git 1.7.8 o posterior) se eliminarán del árbol de trabajo, ya que su repositorio vive dentro del directorio .git del superproyecto. Si un submódulo (o uno de los anidados dentro de él) todavía usa un directorio .git, `git rm` moverá el directorio git de los submódulos al directorio git de superproyectos para proteger el historial del submódulo. Si existe, la sección submodule.\<name> del archivo *gitmodules* también se eliminará y ese archivo se almacenará provisionalmente (a menos que se utilicen `--cached` o `-n` 

Un submódulo se considera actualizado cuando el *HEAD* es el mismo que se registra en el índice, no se modifican los archivos con seguimiento y no hay archivos sin seguimiento que no se ignoren en el árbol de trabajo de los submódulos. Los archivos ignorados se consideran prescindibles y no impedirán que se elimine el árbol de trabajo de un submódulo.

Si sólo desea eliminar la extracción local de un submódulo del árbol de trabajo sin confirmar la eliminación, utilice ``git-submodule`` `deinit` en su lugar. Consulte también gitsubmodules para obtener detalles sobre la eliminación de submódulos.

## Ejemplos de eliminación

    git rm Documentation/\*.txt

Quita todos los archivos *.txt del índice que se encuentran en el directorio `Documentation` y cualquiera de sus subdirectorios.

Tenga en cuenta que el asterisco \* se cita del shell en este ejemplo; esto permite a Git, y no el shell, expandir los nombres de ruta de acceso de los archivos y subdirectorios en el directorio `Documentation`.

    git rm -f git-*.sh

Dado que este ejemplo permite que el shell expanda el asterisco (es decir, que enumera los archivos explícitamente), no quita ``subdir/git-foo.sh``.

Ahora veremos un procedimiento para eliminar carpetas/archivos.

Primero iremos a la carpeta que queremos eliminar, veremos que hay donde estamos.

~~~bash
David@Ciri MINGW64 ~
$ ls -la

drwxr-xr-x 1 David 197609       0 Oct  8 10:20  JavaScript/
drwxr-xr-x 1 David 197609       0 Oct  9 17:50  Launch_X/
drwxr-xr-x 1 David 197609       0 Jan  3  2021  Links/
lrwxrwxrwx 1 David 197609      59 Jan  3  2021 'Menú Inicio' -> '/c/Users/David/AppData/Roaming/Microsoft/Windows/Start Menu'/
~~~

Cambiamos a la carpeta:

~~~bash
David@Ciri MINGW64 ~
$ cd Launch_X/

David@Ciri MINGW64 ~/Launch_X (master)
~~~

Revisamos el contenido y nos ubicamos donde queremos.

~~~bash
David@Ciri MINGW64 ~/Launch_X (master)
$ ls -l
total 5
-rw-r--r-- 1 David 197609 337 Sep 29 00:06 Notas_de_commit
drwxr-xr-x 1 David 197609   0 Oct 14 00:11 Practica1/
drwxr-xr-x 1 David 197609   0 Sep 30 22:40 Practica1_Ejemplo/

David@Ciri MINGW64 ~/Launch_X (master)
$ cd Practica1_Ejemplo/MissionFrontEnd
~~~

Ahora revisemos

~~~Bash
David@Ciri MINGW64 ~/Launch_X/Practica1_Ejemplo/MissionFrontEnd (main)
$ ls
'01 - Intro'/  'Practica html'/  'practicas extras'/
~~~

Bueno, eliminaremos la carpeta de practicas extras y sus archivos

~~~Bash
David@Ciri MINGW64 ~/Launch_X/Practica1_Ejemplo/MissionFrontEnd (main)
$ git rm practicas\ extras/\*.*
rm 'practicas extras/index.html'
rm 'practicas extras/logo.png'
rm 'practicas extras/pedido.html'
rm 'practicas extras/taqueria.html'
~~~

Ayudandonos con el comodín \* aprovechamos de eliminar archivos de todos los tipos, cuidado con lo que borras.
Ahora revisemos que nos queda

~~~Bash
David@Ciri MINGW64 ~/Launch_X/Practica1_Ejemplo/MissionFrontEnd (main)
$ ls
'01 - Intro'/  'Practica html'/
~~~

Revisando Practica html, también lo eliminare completamente

~~~Bash
David@Ciri MINGW64 ~/Launch_X/Practica1_Ejemplo/MissionFrontEnd (main)
$ git rm Practica\ html/\*.*
rm 'Practica html/admin.css'
rm 'Practica html/admin.html'
rm 'Practica html/assets/chocolate.jpg'
rm 'Practica html/assets/fondo-landing.jpg'
rm 'Practica html/assets/foto-comestible.jpg'
rm 'Practica html/assets/fresa.jpg'
rm 'Practica html/assets/ingresos.png'
rm 'Practica html/assets/logo.svg'
rm 'Practica html/assets/muñecos.jpeg'
rm 'Practica html/assets/pedido-sin-fondo.png'
rm 'Practica html/assets/ubicacion.png'
rm 'Practica html/assets/vainilla.jpg'
rm 'Practica html/assets/velas.jpg'
rm 'Practica html/index.html'
rm 'Practica html/style.css'
~~~

Reviso.

~~~Bash
David@Ciri MINGW64 ~/Launch_X/Practica1_Ejemplo/MissionFrontEnd (main)
$ ls
'01 - Intro'/

David@Ciri MINGW64 ~/Launch_X (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    Practica1_Ejemplo/MissionFrontEnd

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Practica1/README.md
        modified:   Practica1/publicoObjetivo/README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Practica1_Ejemplo/
~~~

Una vez realizados los `add`, `commit` y `push` necesarios, ahora sí a comenzar con mis trabajos de prácticas y evitar que tengan conflictos con prácticas pasadas, porque ya voy tarde =P


[Siguiente **&#129042;**](014_Recuperar_Archivos_anteriores.md "Recuperar archivos")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")



