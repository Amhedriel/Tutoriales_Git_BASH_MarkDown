# Comandos básicos en Bash

Tenemos varios comandos básicos que serán muy útiles en el manejo de nuestro Bash, para poder movernos rápidamente al igual que crear, mover, arreglar, copiar, eliminar, etc. porque aunque uno al principio no lo crea, con solo comandos podemos realizar varias acciones a una gran velocidad exeptuado la edición de código en sí, para lo cual usaremos un IDE como Visual Studio Code.

Ahora veremos algunos comandos importantes:

* [pwd](#visualizar-carpeta-actual-pwd)
* [mkdir](#crear-carpetas-mkdir)
* [rmdir](#rmdir)
* [ls](#listar-ls)
* [cd](#movernos-entre-carpetas-cd)
* [touch](#crear-archivos-touch)
* [vim](#vivim-editor-de-texto-plano)
* [cat](#mostrar-contenido-de-un-archivo-cat)
* [history](#history-historial-de-comandos)
* [clear](#limpiar-pantalla-clear)
* [rm](#rm-borrar-archivos)
* [cp](#cp-copy)
* [mv](#mover-renombrar-directoriosarchivos-mv)
* [--help](#ayuda-cualquier-comando-seguido-de---help)



## Visualizar carpeta actual "pwd"
Para poder visualizar en que carpeta estamos trabajando actualmente usando el comando `pwd` nos mostrará:

~~~
David@Ciri MINGW64 ~/Dropbox
$ pwd
/c/Users/David/Dropbox
~~~

Lo que nos indica que nuestra carpeta de trabajo actual es `Dropbox`.

---

## Crear carpetas "mkdir"
Para crear carpetas mediante el terminal:

~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ mkdir miweb
~~~

 Así creamos un directorio llamado `miweb`

---

## rmdir

Con este comando borraremos un directorio vacío.

    $ rmdir miweb

---

## Listar "ls"
Con este comando podremos ver un listado de todos los archivos y carpetas que se encuentran dentro de un determinado directorio, en este caso sería dentro del directorio en el que nos encontramos trabajando

~~~Bash
David@Ciri MINGW64 ~/Dropbox
$ ls

'01 Linux'/      AlexaStudio/    batch1.pdf          DavidIconor.jpg    DiabloSave/            Guia2.txt                 Imagenes/      'Mi PC (Ciri)'/  'Nueva carpeta'/  'Programas escenciales'/   Utilitarios/
 01Libors/       amor.txt        Coins/              DavidIconor1.ico  'Disco Duro Semprom'/   Hack_x_Crack_batch2.pdf   ImgOneNote/     miarchivo.txt    pagare.docx       save/                     Video/
 1993.txt        Aplicaciones/   DavidIcono300.jpg   DavidIconor2.jpg   Documentos/            HxC05.pdf                 Loquendo/       Musica/         'PC (2)'/         'Subidas desde cámara'/    VisualStudioCode/
 AlexaProject/   Aprender/       DavidIcono300.png   desktop.ini        Estudiar/             'Imagen sin título.png'   'Marketing 1'/   noticias/        PDF/              Tipografias/
~~~

Para forzar a mostrar en pantalla archivos ocultos podemos utilizar el comando `ls -a`
`ls -al`es un argumento el espacio significa que el comando principal es ls y guón - que estoy traendo argumentos especiales al comando y en este caso es que me muestre todos los archivos incluso los ocultos y los ordene en una lista.
~~~

$ ls -al
total 9539
drwxr-xr-x 1 David 197609       0 Aug  3 21:32  ./
drwxr-xr-x 1 David 197609       0 Aug 19 23:20  ../
-rw-r--r-- 1 David 197609      41 Dec 27  2020  .dropbox
drwxr-xr-x 1 David 197609       0 May  7 01:10  .dropbox.cache/
drwxr-xr-x 1 David 197609       0 Dec 27  2020 '01 Linux'/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  01Libors/
-rw-r--r-- 1 David 197609      76 Aug  4  2013  1993.txt
drwxr-xr-x 1 David 197609       0 Jan 15  2021  AlexaProject/
drwxr-xr-x 1 David 197609       0 Jan 15  2021  AlexaStudio/
drwxr-xr-x 1 David 197609       0 Jan 18  2021  Aplicaciones/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  Aprender/
drwxr-xr-x 1 David 197609       0 May  6 15:45  Coins/
-rw-r--r-- 1 David 197609   52412 Nov 26  2014  DavidIcono300.jpg
-rw-r--r-- 1 David 197609  166250 Nov 26  2014  DavidIcono300.png
-rw-r--r-- 1 David 197609   10818 Oct 17  2014  DavidIconor.jpg
-rw-r--r-- 1 David 197609    2238 Oct 17  2014  DavidIconor1.ico
-rw-r--r-- 1 David 197609   10895 Oct 17  2014  DavidIconor2.jpg
drwxr-xr-x 1 David 197609       0 Dec 27  2020  DiabloSave/
drwxr-xr-x 1 David 197609       0 Dec 27  2020 'Disco Duro Semprom'/
drwxr-xr-x 1 David 197609       0 Feb  9  2022  Documentos/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  Estudiar/
-rw-r--r-- 1 David 197609   33512 Nov 16  2014  Guia2.txt
-rw-r--r-- 1 David 197609 2609809 Jul 21  2012  Hack_x_Crack_batch2.pdf
-rw-r--r-- 1 David 197609 4296873 Jul 21  2012  HxC05.pdf
-rw-r--r-- 1 David 197609   69042 Oct  3  2014 'Imagen sin título.png'
drwxr-xr-x 1 David 197609       0 Apr 10  2021  Imagenes/
drwxr-xr-x 1 David 197609       0 Jan 15  2021  ImgOneNote/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  Loquendo/
drwxr-xr-x 1 David 197609       0 Dec 27  2020 'Marketing 1'/
drwxr-xr-x 1 David 197609       0 Dec 27  2020 'Mi PC (Ciri)'/
drwxr-xr-x 1 David 197609       0 Jan 18  2021  Musica/
drwxr-xr-x 1 David 197609       0 Feb 21  2021 'Nueva carpeta'/
drwxr-xr-x 1 David 197609       0 Dec  1  2021 'PC (2)'/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  PDF/
drwxr-xr-x 1 David 197609       0 Jan 26  2022 'Programas escenciales'/
drwxr-xr-x 1 David 197609       0 Dec 27  2020 'Subidas desde cámara'/
drwxr-xr-x 1 David 197609       0 Dec 27  2020  Tipografias/
drwxr-xr-x 1 David 197609       0 May  6 15:42  Utilitarios/
drwxr-xr-x 1 David 197609       0 Jan 29  2021  Video/
drwxr-xr-x 1 David 197609       0 Aug  8 16:00  VisualStudioCode/
drwxr-xr-x 1 David 197609       0 Aug  3 21:33  Workspace/
-rw-r--r-- 1 David 197609      48 Mar 22  2013  amor.txt
-rw-r--r-- 1 David 197609 2292043 Nov 21  2012  batch1.pdf
-rw-r--r-- 1 David 197609     176 May  6 15:58  desktop.ini
-rw-r--r-- 1 David 197609      67 Oct  3  2014  miarchivo.txt
drwxr-xr-x 1 David 197609       0 Jan 15  2021  noticias/
-rw-r--r-- 1 David 197609   24649 Mar  9  2016  pagare.docx
drwxr-xr-x 1 David 197609       0 Dec 27  2020  save/
~~~

## Movernos entre carpetas "cd"
Con este comando podremos movernos entre carpetas ya sea a una en concreto, retroceder, buscar entre toda la PC, Raíz, etc.

~~~
David@Ciri MINGW64 ~/Dropbox
$ cd VisualStudioCode/

David@Ciri MINGW64 ~/Dropbox/VisualStudioCode
$
~~~

Al escribir el comando de `ls` y una ruta nos cambiaremos a esa ruta como se muestra en el comando de arriba.

Ahora bien, si queremos regresar al directorio en el que nos encontrabamos inicialmente:

~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode
$ cd ..

David@Ciri MINGW64 ~/Dropbox
$
~~~

Asi regresaremos a la carpeta de la anterior jerarquía.


### TIP: Comodines
Utilizar el tab para autocompletar los nombres de los Archivos/Directorios que vayamos a referenciar.

---

## Crear archivos touch
Para crear archivos de texto plano y editarlos podemos utilizar `vi/vim` o si solo queremos crear un archivo vacio utilizaremos `touch` seguido del nombre del archivo que deseamos crear.

~~~
David@Ciri MINGW64 ~/Git
$ touch vacio.txt

David@Ciri MINGW64 ~/Git
$ ls
vacio.txt
~~~

---

## Vi/Vim Editor de texto plano

Es un editor de texto compjeto y completo, esta desde el principio de Bash, más tarde se agregaron otros con herramientas más fáciles de manejar pero son editores externos que no necesariamente pueden estar en todos los entornos de Bash existentes, personalmente Vim es el editor que yo uso y aunque suele ser abrumador la cantidad de usos y herramientas que tiene es realmente bueno.

~~~Bash
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown/BASH (master)
$ vim 004_Vim.md
~~~

Con este comando estamos creando un archivo "004_Vim" con la extención de MarkDown ".md" y lo editaremos con Vim ``"vim"``

~~~Bash
$ cat 004_Vim.md
Debemos recordar que una manera de empezar a editar código en Vim debemos presionar la tecla **Insert**, también que el mouse no sirve acá ni algunas teclas rápidas de conocimiento general.

Para grabar lo escritio presionar **Esc** luego **:w** y después **:q** por si quieres salir, ahora si quieres guardar y salir en este orden con un solo comando **:wq**.
~~~

Aqui podemos ver el resultado con el comando `cat`

### Salir de Vi/Vim

Para poder salir del editor guardando los cambios debemos presionar ESC y luego :exit o :q! con este comando descartará todos los cambios realizados.

---

## Mostrar contenido de un archivo cat

Para mostrar el contenido de un archivo podemos utilizar `cat`

~~~
David@Ciri MINGW64 ~/Git
$ cat vacio.txt
Mensaje secreto.
~~~

---

## history historial de comandos

Para poder revisar el listado completo de todos los comandos que estamos utilizando podemos utilizar `history`.

~~~
$ history
    1  ls
    2  dir
    3  cd ..
    4  ls
    5  cd ~
    6  ls
    7  exit
    8  git help
    9  q
   10  quit
   11  exit
   12  ls
   13  cd Documents/
   14  ls
   15  cd ..
   16  cd Dropbox/VisualStudioCode/
   17  ls
   18  md miweb
   19  mkdir miweb
   20  ls
    .
    .
    .
  230  cd Git/
  231  touch vacio.txt
  232  ls
  233  cat vacio.txt
  234  vi vacio.txt
  235  cat vacio.txt
  236  history
~~~
Para poder volver a utilizar un comando pueden hacer una invocación con el número de identificador que tiene, por ejemplo si yo quiero crear otra carpeta con el nombre de mi web podemos utilizar `!` seguido del número `19`.

~~~
David@Ciri MINGW64 ~/Git
$ !19
mkdir miweb

David@Ciri MINGW64 ~/Git
$ ls
miweb/  vacio.txt
~~~

---

## Limpiar pantalla clear

El comando para poder limpiar la pantalla es `clear` y borrara todo lo que esta en pantalla, no borra los cambios realizados, solo limpia la pantalla al igual que `cls` o `clscream` en DOS.

Pero en Bash el comando rápido para limpiar pantalla es CTRL+L.

---

## rm Borrar archivos

Para poder borrar archivos con la línea de comandos utilizaremos `rm`seguido del nombre del o de los archivos a eliminar separados por un espacio.

~~~
David@Ciri MINGW64 ~/Git
$ ls
miweb/  vacio.txt  vacio1.txt

David@Ciri MINGW64 ~/Git
$ rm vacio1.txt vacio.txt

David@Ciri MINGW64 ~/Git
$ ls
miweb/
~~~

### NOTA

Este comando es muy peligros, porque, puede borrar incluso el disco duro sin necesidad de confirmación.

---
## cp copy 

Comando útil para copiar archivos de una carpeta a otra sin perder nada del contenido

    $ cp carpeta1/carpeta2/arcvivo1.txt carpeta1/carpeta3/archivo1.txt

Con esto copiamos el contenido del "archivo1.txt" de la "carpeta2" a la "carpeta3" 

## Mover, renombrar directorios/archivos mv

El comando `mv` (move), mueve archivos y directorios de un lugar a otro. También puede ser usado para renombrar archivos y directorios.

  mv [options] source destination

El `source` puede ser uno o más archivos/directorios, el `destination` es siempre un solo archivo/directorio que se escribe en último lugar.

### Mover un archivo a un directorio

  mv <filename> <path_of_destinationDirectory>

Si el directorio de destino no existe, el archivo se renombrará como el archivo de destino.

Si la ruta de destino es un archivo, el archivo fuente se renombra con el primero.

  mv illunee.svg 1.svg

Se renombrará el archivo `illunee.svg` a `1.svg`

En algunos casos el archivo de destino puede existir y será sobrescrito si usamos `mv`. Para pedir confirmación antes de sobrescribir, usaremos la opción `-i`  con el comando `mv`

Para evitar la sobrescritura, presione `N` y Enter, si no, `Y`

### Mover un directorio dentro de otro directorio

    mv <path_of_source_directory> <path_of_destination_directory>

  mv Python_Scripts Python_Scripts_New

Mueve el directorio `Python_Scripts` en nuestro directorio de trabajo actual dentro de otro directorio `Python_Scripts_New` en el directorio de trabajo actual.

Si el directorio de destino no está presente, el directorio de origen es renombrado al directorio de destino

### Mover Múltiples archivos

Para mover varios archivos dentro de otro directorio, especificamos todos los archivos de origen seguido de la ruta del directorio de destino.

    mv <source_filepath_1> <source_filepath_2> <source_filepath_3> <path_of_destination_directory>

    mv 1.jpg 2.jpg 2.png Images

Mueve los archivos `1.jpg`,`2.jpg` y `2.png` en nuestro directorio de trabajo actual dentro de otro directorio `Images` en el directorio de trabajo actual.

También podemos mover múltiples archivos dentro de un directorio usando expresiones regulares para que coincidan con los nombres de los archivos que necesitan ser movidos.

    mv *.jpg JPG-Images

### Hacer copia de seguridad de un archivo existente

Para hacer una copia de seguridad usamos la opción `-b`. Crea una copia sobrescrita con el caracter `~` adjunto al nombre de archivo de copia de seguridad.

~~~bash
$ mv -b abc.jpg 123.jpg
ls

123.jpg 123.jpg~
~~~

### Parámetros

OPCIÓN | DESCRIPCIÓN
--- | :---: 
`-a, -archive` | Combina opciones y `d p r`
`-b, -backup` | Hacer una copia de seguridad
`-d, --no-deference` | Conserva los enlaces
`-f, --force` | Borram los existentes en el destino sin preguntar
`-i, --interacive` | Mostrar mensajes antes de reemplazar
`-l, --link` | En lugar de copiar, vincula el archivo en su lugar
`-p, --preserve` | Conservar los atributos del archivo cuando sea posible
`-R, --recursive` | Copiar directorios de forma recursiva

---

## Ayuda cualquier comando seguido de --help

Para tener ayuda con respecto a las opciones posibles con comando podemos utilizar un comando cualquiera seguido de la opción de `--help`

~~~
$ rm --help
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or
                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes
      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat '/' specially
      --preserve-root[=all]  do not remove '/' (default);
                              with 'all', reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a '-', for example '-foo',
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/rm>
or available locally via: info '(coreutils) rm invocation'
~~~

[Siguiente **&#129042;**](/BASH/002_Directorios.md "Directorios")

---

[*Volver* **&ldca;**](/BASH/README.md "A README") [*Subir* **&#11165;**](# "Ir al título")