# Comandos básicos

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

---
## Visualizar carpeta actual "pwd"
Para poder visualizar en que carpeta estamos trabajando actualmente usando el comando `pwd` nos mostrará:

~~~
David@Ciri MINGW64 ~/Dropbox
$ pwd
/c/Users/David/Dropbox
~~~

Lo que nos indica que nuestra carpeta de trabajo actual es `Dropbox`.

---
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


### TIP:
Utilizar el tab para autocompletar los nombres de los Archivos/Directorios que vayamos a referenciar.

---
## Crear carpetas "mkdir"
Para crear carpetas mediante el terminal:

~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ mkdir miweb
~~~
 Así creamos un directorio llamado `miweb`

---
## Crear un repositorio "git init"

Ahora bien aplicando todo lo aprendido más arriba crearemos un directorio para empezar a practicar con Git:

primero, revisamos donde estamos

~~~
David@Ciri MINGW64 ~/Dropbox
$ pwd
/c/Users/David/Dropbox
~~~

Segundo, listamos las carpetas para poder movernos

~~~Bash
David@Ciri MINGW64 ~/Dropbox
$ ls

'01 Linux'/      AlexaStudio/    batch1.pdf          DavidIconor.jpg    DiabloSave/            Guia2.txt                 Imagenes/      'Mi PC (Ciri)'/  'Nueva carpeta'/  'Programas escenciales'/   Utilitarios/
 01Libors/       amor.txt        Coins/              DavidIconor1.ico  'Disco Duro Semprom'/   Hack_x_Crack_batch2.pdf   ImgOneNote/     miarchivo.txt    pagare.docx       save/                     Video/
 1993.txt        Aplicaciones/   DavidIcono300.jpg   DavidIconor2.jpg   Documentos/            HxC05.pdf                 Loquendo/       Musica/         'PC (2)'/         'Subidas desde cámara'/    VisualStudioCode/
~~~

Creamos un par de carpetas en `Dropbox/` para comezar a trabajar.

    $ mkdir ~/Dropbox/Workspace/miweb

Ahora nos movemos a esas carpetas recién creadas.

    $ cd ~/Dropbox/Workspace/miweb

Y comprobamos estar en donde deberíamos estar.

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb
$ pwd
/c/Users/David/Dropbox/Workspace/miweb
~~~

Por último inicializamos un repositorio como si fuese un proyecto que gestionaremos con Git:

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb
$ git init

Initialized empty Git repository in C:/Users/David/Dropbox/Workspace/miweb/.git/

David@Ciri MINGW64 ~/Dropbox/Workspace/miweb (master)
$
~~~

Ahora bash nos indica que a inicializado un repositorio en Git completamente vacío dentro de `C:/Users/David/Dropbox/Workspace/miweb/.git/`(recordar que esa última carpeta se encuentra oculta, a menos que utilicemos el comando `ls -a`)

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb (master)
$ ls -a
./  ../  .git/
~~~
Debemos recordar que el punto (.) significa que estamos en ese directorio actualmente, el dobel punto (..) es para retroceder un directorio y `.git` es en donde ingresaremos ahora.

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb (master)
$ cd .git

David@Ciri MINGW64 ~/Dropbox/Workspace/miweb/.git (GIT_DIR!)
$
~~~

Ahora estamos dentro de `.git`

Si queremos ver todos los archivos ocultos que se utilizan en Git para poder gestionar nuestros proyectos:

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb/.git (GIT_DIR!)
$ ls -a

./  ../  config  description  HEAD  hooks/  info/  objects/  refs/
~~~

Esto es un detalle de implementación, aqui es donde se van a almacenar las distintas versiones de nuestro código, las distintas ramas, los commits, absolutamente todo. Estos son detalles de implementación en cuanto cómo va a utilizar el código por lo que no nos interesa, lo que nos compete es aprender a utilizar los comandos.

### NOTA
La carpeta `.git` es completamente ignorada y esta no pasa a un servidor central o no se comparte entre los desarrolladores.

___
## Limpiar pantalla CLEAR

El comando para poder limpiar la pantalla es `clear` y borrara todo lo que esta en pantalla, no borra los cambios realizados, solo limpia la pantalla al igual que `cls` o `clscream` en DOS.

Pero en Bash el comando rápido para limpiar pantalla es CTRL+L.

---
## PWD
con este comando visualizamos en la carpeta que nos encontramos.

~~~
David@Ciri MINGW64 ~/Dropbox/Workspace/miweb
$ pwd
/c/Users/David/Dropbox/Workspace/miweb
~~~

---
## Crear archivos
Para crear archivos de texto plano y editarlos podemos utilizar `vi/vim` o si solo queremos crear un archivo vacio utilizaremos `touch` seguido del nombre del archivo que deseamos crear.

~~~
David@Ciri MINGW64 ~/Git
$ touch vacio.txt

David@Ciri MINGW64 ~/Git
$ ls
vacio.txt
~~~

---
## Mostrar contenido de un archivo CAT

Para mostrar el contenido de un archivo podemos utilizar `cat`

~~~
David@Ciri MINGW64 ~/Git
$ cat vacio.txt
Mensaje secreto.
~~~

---
## Salir de Vi/Vim

Para poder salir del editor guardando los cambios debemos presionar ESC y luego :exit o :q! con este comando descartará todos los cambios realizados.


---
## Historial de comandos HISTORY

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
## Borrar archivos RM

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

[Siguiente **&#129042;**](006_Flujo_De_Trabajo_Git.md "Flujo de trabajo con Git")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")
