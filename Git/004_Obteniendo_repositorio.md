# Fundamentos de Git - Obteniendo un repositorio Git
Este capítulo cubre los comandos básicos para hacer la gran mayoría de cosas a las que eventualmente vas a dedicar tu tiempo mientras trabajas con Git. Deberás ser capaz de configurar e inicializar un repositorio, comenzar y detener el seguimiento de archivos, y preparar (stage) y confrmar (commit) cambios. Configurar Git para ignorar ciertos archivos y patrones, cómo enmendar errores rápida y fácilmente, cómo navegar por el historial y ver cambios entre confirmaciones, cómo evitar (push) y recibir (pull) de repositorios remotos.

* [Crea tu primer repositorio](#crea-tu-primer-repositorio)
* [Obteniendo un repositorio Git](#obteniendo-un-repositorio-git)
    * [Inicializando un repositorio en un directorio existente](#inicializando-un-repositorio-en-un-directorio-existente)
    * [Clonando un repositorio existente](#clonando-un-repositorio-existente)
    * [NOTA:](#nota)


## Crea tu primer repositorio

En GitBash verifiquemos:

    $ git --version
    git version 2.38.0.windows.1

Ahora debemos navegar hasta el directorio que deseamos colocar bajo el control de versiones y crear un repositorio de Git vacío:

    $ git init

Con esto tenemos inicializado el directorio para trabajar con Git, por defecto estará en el *branch* **master** o **main**.
También crea una carpeta oculta `.git`, que contiene todo lo necesario para que Git funcione.

A continuación. verifiquemos qué archivos Git agregaremos a nuestro repositorio:

    $ git status

Revisamos la lista resultante de archivos; podemos decirle a Git cuál de los archivos queremos colocar en el control de versiones (No enviar información confidencial, como contraseñas o archivos que solo saturan el repositorio como videos o imágenes, estos archivos grandes se recomiendan agregarlos mediante anclas, por estar almacenados en servidores externos y no en el mismo directorio del proyecto):

    $ git add <file/directory name #1> <file/directory name #2> < ... >

Si todos los archivos de la lista deben compartirse con todos los que tienen acceso al repositorio, un solo comando agregará todo en su directorio actual y sus subdirectorios:

    $ git add .

Esto "preparará" todos los archivos que se agregarán al control de versiones, preparándolos para que se confirmen en su primer confirmación.

Para los archivos que no desee que se suban al repositorio entonces cree un archivo ``.gitignore`` antes de ejecutar el comando ``add``.

Confirmamos todos los archivos que se han agregado, junto con un mensaje de confirmación:

    $ git commit -m "Initial commit"

Esto crea una nueva confirmación con el mensaje dado. Un `commit` (comprometer?) es como guardar de manera instantánea de todo su proyecto. Ahora puede enviarlo o cargarlo a un repositorio remoto, y más tarde puede volver a él si es necesario. Si omitimos el parámetro `-m`, su editor predeterminado se abrirá y podrá editar y guardar el mensaje de confirmación en este editor.


## Obteniendo un repositorio Git
Puedes obtener un proyecto de Git de 2 maneras. La primera es tomar un proyecto o directorio existente e importarlo en Git. La segunda es clonar un repositorio existente en Git desde otro servidor.

### Inicializando un repositorio en un directorio existente
Si estás empezando a seguir un proyecto existente en Git, debes ir al directorio del proyecto y usar el siguiente comando:

    $ git init

Esto crea un subdirectorio llamado .git(que por empezar con un dot o punto sera un directorio oculto), el cual tiene todos los archivos necesarios del repositorio - un esqueleto de un repositorio Git. Todavía no hay nada en tu proyecto que esté bajo seguimiento. Puedes revisar [ch 10-git-imternals] para obtener más información acerca de los archivos presentes en el directorio `.git` que acaba de ser creado.

Si deseas empezar a controlar versiones de archivos existentes (a diferencia de un directorio vacío), probablemente deberías comenzar el seguimiento de esos archivos y hacer una confirmación inicial. Puedes conseguirlo con unos pocos comandos `git commit` para confirmar los cambios:
~~~
$ git add *.c
$ git add LICENSE
$ git commit -m 'initial project version'
~~~
En este momento, tienes un repositorio de Git con archivos bajo seguimiento y una confirmación inicial.

### Clonando un repositorio existente
Si deseas obtener una copia de un repositorio Git existente - por ejemplo, un proyecto en el que te gustaría contribuir - el comando es `git clone`. Git recibe una copia de casi todos los datos que tiene el servidor. Cada versión de cada archivo del historial del proyecto es descargada por defecto cuando ejecutas `git clone`. De hecho, si el disco de ti servidor se corrompe, puedes usar cualquiera de los clones en cualquiera de los clientes para devolver el servidor al estado en el que estaba cuando fue clonado (Puede que pierdas algunos hooks del lado del servidor y demás, pero toda la información acerca de las versiones estará ahí) - véase *Configurando Git en un servidor* para más detalles.

Puedes clonar un repositor con `git clone [url]`. Por ejemplo, si quieres clonar la librería de Git llamada libgit2 puedes hacer algo así:

    $ git clone https://github.com/libgit2/libgit2

Esto crea un directorio llamado `gitlib2`, inicializa un directorio `.git` en su interior, descarga toda la información de ese repositorio y saca una copia de trabajo de la última versión. Si te metes en el directorio `libgit2`, verás que están los archivos del proyecto listo para ser utilizados. si quieres clonar el repositorio de un directorio con otro nombre que no sea `libgit2` puedes especificarlo con la siguiente opción de línea de comandos:

    $ git clone https://github.com/libgit2/libgit2 mylibgit

Ese comado hace lo mismo que el anterior, pero el directorio de destino se llamará `mylibgit`.

### NOTA: 
Git te permite usar distintos protocolos de transferencia. El ejemplo anterior usa el protocolo `https://` pero también puedes utilizar `git://` o `usuario@servidor:ruta/del/repositorio.git` que utiliza el protocolo de transferencia SSH. En *Configurando Git en un servidor* se explicarán todas las opciones disponibles a la hora de configurar el acceso a tu repositorio de Git, y las ventajas e inconvenientes de cada una.

[Siguiente **&#129042;**](/Git/004.1_Clonaci%C3%B3n_De_Reposirotios.md "Comandos básicos")


---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")
