# fork en GitHub

Si en GitHub podemos ver un repositorio que sea de nuestro agrado y queremos tener una copia para hacer algunas modificaciones, entonces usamos la funcionalidad de `fork`.

## fork

Si quisieramos tener una copia de algún repositorio y poder hacer cambios con nuestra propia adaptación entonces:

* Vamos al repositorio.
* Hacemos un `fork` clickeando en **fork**.
* Podremos verlo en nuestro repositorio personal.

Ahora los cambios que realizemos se verán reflejados en nuestra copia local y no en la principal.

## Pasos a seguir

1. Creamos una carpeta.
2. Abrir la terminal (bash) en dicha carpeta.
3. Ejecutar `git clone` con la ruta que **GitHub** nos proporciona en "Clone or download".
   Con esto descargará el repositorio a nuestra máquina.
4. Con `cd` cambiamos a la carpeta que clonamos y podemos ver todo lo descargado con `ls -l`.

Con esto ya podremos manejar libremente todos los archivos obtenidos.

## commit

Podemos agregar los cambios que realicemos al proyecto:

1. `git add .` el punto en caso que queramos subir todos los archivos o revisar ``git ignore``.
2. `git commit -m "Cambios relizados en..."` para commitear los cambios que hicimos eh informar los cambios realizados.
3. `git push origin master` aunque en algunos casos se utiliza `main` en lugar de `master` que indica tu *branch* (rama) principal.
4. Indicamos nuestras credenciales `username` y `password`.

Nuestros cambios son enviados a GitHub y podemos verlo en nuestro repositorio.

## No perdemos los cambios

Si hacemos un `fetch` y lugo un `ferch` y los cambios en nuestra *rama* no entran en conflicto entonces no se pierden nuestros cambios, pero, si estan en conflicto GitHub nos indicará algo como: "Tu rama está Nº commit´s por delante".

## fork con git para sincronizar nuestro repositorio
Imagínate que no tenemos disponible GitHub o que la empresas en la que estemos trabajando no utilize una plataforma de desarrollo colaborativo de software para alojar proyectos con el botón de `fork`.

Hagamos entonces:

* `git remote` que nos muestra los repositorios remotos en los que están conectados tu repositorio local.

~~~
$ git remote
origin
~~~

Nos muestra los repositorios remotos a los que está conectado nuestro repositorio local, ahora nos indica *origin*. El repositorio remoto es el que tenemos en GitHub y es *origin*, el local es el que estamos manejando.

* `git remote -v`

Para verlo algo mejor utilizaremos `-verbose`

~~~
$ git remote -v
origin  https://github.com/....git (fetch)
origin  https://github.com/....git (push)
~~~

Los repositorios remotos que tengo:
1. Con el alias *origin* que va con la primera dirección que corresponde a la direccion de GitHub (fetch)
2. Y *origin* con la dirección de nuestro reositor local (push)

Como se puede observar son 2 direcciones de *origin* uno para hacer el `fetch` y el otro para hacer el `push`, lo normal es que coincidan.

Nuestro repositro local está conectado a un repositor remoto en la nube, ahora si tuvieramos otro repositor remoto de donde queramos recuperar cambios le podemos añadir otro `remote`.

* `git remote add alias`

En donde ``alias`` se le suele llamar **`upsrteam`** porque sería la fuente de datos de más arriba de donde has hecho el `fork`.

    $ git remote add upstream https://github.com/....git

Y ahora haremos un:

~~~bash
$ git remote -v
origin  https://github.com/....git (fetch)
origin  https://github.com/....git (push)
upstream        https://github.com/....git (fetch)
upstream        https://github.com/....git (push)
~~~

Podemos ver `origin` y que añadió `upstream`, ahora podemos hacer un montón de cosas como:

* `git fetch origin`
* `git fetch upstream`

Y con esto nos va a traer todos los cambios de todas las ramas que se han hecho en el `upstream` y ahora soy capaz de ver los 2 repositorios a la vez.

Ahora podemos hacer:

* `git pull origin` El origin es el repositorio remoto al que nos referimos.
* `git pull upstream main` Con esto nos podríamos traer los cambios de *main*.

Haciendo estos pasos cuando tu tengas un fork de una forma como esta podrías estar constantemente sincronizando el repositorio porteado con el *original*.



