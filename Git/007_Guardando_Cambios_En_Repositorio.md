# Guardando cambios en el repositorio

Ya tienes un repositorio Git y un *checkout* o copia de trabajo de los archivos de dicho proyecto. el siguiente paso es realizar algunos cambios y confirmar instantáneas de esos cambios en el repositorio cada vez que el proyecoto alcance un estado que quieras conservar.

Cada archivo de tu repositorio tiene 2 estados: rastreados y sin rastrear. Los *tracked files* o rastreados son todos aquellos archivos que estaban en la última instantánea del proyecto; pueden ser archivos sin modificar, modificados o preparados. Los archivos sin rastrear son todos los demás - cualquier otro archivo que no estaba en tu directorio de trabajo que no estaba en tu última instantánea y que no está en el área de preparación *staging area*. Cuando clonas por primear vez un repositorio, todos tus archivos estarán rastreados y sin modificar pues acabas de sacarlos y aun no han sido editados.

Mientras editas archivos, Git los ve como modificados, pues han sido cambiados desde su último **commit**. Luego preaparas estos archivos modificados y finalmente confirmas todos los cambios preparados, y repites el ciclo.

| UNTRACKED     | UNMODIFIED      | MODIFIED     | STAGED        |
|---------------|-----------------|--------------|---------------|
| Add the file  |-----------------|--------------|-------------->|
|               |Edit the file--->|              |               |
|               |                 |Stage file--->|               |
|<---Remove file|                 |              |               |
|               |                 |<-------------|  ---Commit    |

El siclo de vida del estado de tus archivos.

## Revisando el Estado de tus Archivos
La herramienta principal para determinar qué archivos están en qué estado es el comando `git status`.

Si ejecutas es comando después de clonar un repositorio, deberías ver algo como esto:
~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ git status
On branch master
nothing to commit, working directory clean
~~~
Esto significa que tienes un directorio de trabajo limpio, que no hay archivos rastreados y modificados. Además, Git no encuentra archivos sin rastrear, de los contrario aparecerían listados aquí. El comando te indica en cuál rama estás y te informa que no ha variado con respecto a la misma rama en el servidor. Por ahora, la rama siempre será ***"master"***, que es la rama por defecto.

Supongamos que añades un nuevo archivo a tu proyecto, un simple README. Si el archivo no existía antes y ejecutas `git status`, verás el archivo sin rastreae de la siguiente manera:
~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ echo 'My Project' > README
$ git status
On branch master
Untracked files:
    (use "git add <file>..." to include in what will be commit)

      README

nothing added to commit but untracked files present (use "git add" to track)
~~~

Puedes ver que el archivo README está sin rastrear porque aparece debajo del encabezado `untracked files` (Archivos no rastreados) en la salida. Sin rastrear significa que Git ve archivos que no tenías en el **commit** anterior. Git no los incluirá en tu próximo **commit** a menos que se lo indiques explícitamente. Se comporta así para evitar icluir accidentalmente archivos binarios o cualquier otro archivo que no quieras incluir. Como sí quieres incluir README, debes comenzar a rastrearlo.

## Rastrear Archivos Nuevos
Para comenzar a rastrear un archivo debes usar el comando `git add`. Para comenzar a rastrear el archivo README:

    $ git add README

Ahora si vuelves a ver el estado del proyecto, verás que el archivo README está siendo rastreado y está preparado para ser confirmado.

~~~
$ git status
On branch master
Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

      new file:     README
~~~
Puedes ver que está siendo rastreado porque aparece `Changes to be committed:` (`cambios a ser confirmados` en español). si confirmas en este punto, se guardará en el historial la versión del archivo correspondiente al instante en que ejecutaste `git add`. Anteriormente cuando ejecutaste `git init`, luego ejecutaste `git add (files)`- lo cual inició el rastreo de archivos en tu rirectorio, el comando añade recursivamente los archivos que están dentro de él.

[Siguiente **&#129042;**](008_Agregando_Cambios_Stage.md "Agregando cambios a stage")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")
