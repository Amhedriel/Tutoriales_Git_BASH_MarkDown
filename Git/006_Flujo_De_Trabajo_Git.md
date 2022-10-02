# Flujo de trabajo con Git
Ahora veremos el flujo de trabajo que debemos seguir cuando estamos trabajando con Git.

## Cómo trabaja:
Lo primero que veremos es que, cuando estemos trabajando en el **computador** vamos a poder empezar a *agregar* y *modificar* tosdos los archivos que queramos, pero por el simple hecho de *modificar*, *agregar* o *eliminar* archivos en nuestro PC, eso no quiere decir que se agreguen inmediatamente  a un repositorio, para eso ejecutamos un comando: `git add`.

Cuando ejecutemos `git add` lo que haremos sera seleccionar los archivos que nosotros queramos pasar a **stage**, con esto lo que hacemos es querer verificar todos los cambios que nosotros queremos y eventualmente pasar a nuestro repositorio. Cuando estamos en **stage** no necesariamente quiere decir que esto se verá reflejado en el repositorio, esto solo es una etapa intermedia para ese proceso, asi podremos indicar cuales són los cambios que nosotros efectuamos para que estos pasen a nuestro repositorio.

Al revisar nuestra estapa de **stage** quizas no queramos pasar estos cambios a nuestros repositorios asi que podemos volver atrás. Pero, si tenemos todos los archivos y cambios que queremos comprometer y pasar a nuestro repositorio entonces podremos ejecutar el comando `git commit`, y con este comando pasaremos nuestros archivos a la etapa de **commit**, entonces podremos eliminar lo que se encuentra dentro de **stage**.

La última etapa que es "opcional" en donde los cambios que hayamos comprometido **commit** vamos a poder pasarlos a un **server** que se encuentra en la nube como sería Git Hub.

### Repasando en gráfico

| COMPUTADOR    | STAGE           | COMMIT      | SERVER        |
|---------------|:---------------:|------------:|--------------:|
| Programador   | Código 1        | Código 2    | READ.md       |
| Código 1      |                 |             | Index.html    |
| Código 2      |                 |             | Código 2      |

Ahora podría pasar que nosotros vayamos a eliminar un archivo en el **computador**, debemos ejecutar el mismo comando `git add`, de esta manera a la etapa de **stage** agregaremos un archivo que nosotros hemos eliminado, esto  es importante para tener el registro de todo el trabajo que nosotros estamos realizando, nosotros tambien lo podemos comprometer **commit** y luego pasar finalmente al servidor donde este archivo será eliminado del repositorio.

---
## Paso a paso

Empecemos con nuestro directorio de trabajo o entorno de desarrollo personal, primero vamos a la consola y escribimos:

### git init

En el momento en que lo hacemos aparecen 2 conceptos nuevos, un área de preparación o 

### staging

Que es el lugar donde enviamos los archivos antes de mandarlos a la base de datos de cambios hostóricos que le hicimos al proyecto, eso lo llamamos el **reposiotorio local**.
La magia de Git es que en todos los ordenadores de las personas que desarrollan hay una copia exacta de toda la historia del proyecto, por lo tanto nunca jamás vas a perder algo, lo que haces es que cuando quieres agregar un archivo de tu carpeta, de tu directorio, hacia el

### repositorio

Lo primero que haces es ponerlo en el área de preparación que se hace con

### git add

Esto le permite a Git hacer un **tracking** un rastreo de los cambios que ocurran en ese archivo. Para explicarlo de alguna manera, si tu tienes 2 archivos, un `index.html`y un `estilos.css` cuando le haces un `git add index.html` lo estará rastreando, es un archivo track **trackeado** y si a `estilos.css`no lo añades simplemente es **untrack**, no importa los cambios que le hagas Git no se va a enterar y no los va a guardar. Igual, esto es en un lugar temporal que si no haces nada con él eventualmente va a desaparecer, por lo que se llama **garbage collector** que es un sistema para proteger la memoria RAM de tu area de trabajo, eventualmente se va a ir. Para que eso no pase debemos enviarlo como nuestra versión definitiva a nuestro repositorio esos cambios, eso se hace con

### git commit

Lo que hacemos con el **commit** es que enviamos todo lo que esta en **staging** hacia nuestro repositorio definitivo.

Este es el flujo de trabajo común. Pero cuando trabajas en un equipo usando servidor remoto necesitas utilizar 

### Repositorio remoto

Es un lugar donde tienes el mismo repositorio en el que tú estas trabajando pero todo el mundo le manda datos para allá trabajan en local y cuando terminan los vuelven a mandar para que el resto del equipo los pueda ver.

Tipicamente esto es GitHub, GitLab, GitBucket, o cualquier lugar donde tengan un servidor remoto.

Cuando queremos traernos datos de un servidor remoto? lo que hacemos es, en lugar de `git init` debemos clonar

### git clone url

Lo que hace es que con el url la direccion de tu repositorio remoto se trae los archivos a 2 lugares, se trae una copia del master a tu directorio de trabajo, a tu carpeta los archivos tal cual y crea al base de datos de todos los cambios históricos en el repositorio local y deja **staging** quietecito y listo, entonces el flujo de trabajo cambia de la siguiente manera:

Utilizamos `git add` cuando quiero agregar archivos a **staging** y sigo haciendo `git commit` cuando quiero mandarlos al repositorio local, pero cuando estoy listo para que la última versión de esos **commit**, el **HEAD** del master se envie al repositorio donde todo el mundo trabaja hago el

### git push

Con `git push` envio todo esto al servidor remoto, y si hay conflictos lidio yo con ellos.

que pasa cuando ya estoy conectado al *repositorio* remoto, ya lo clone, pero quiero traer una actualización porque alguien más cambió algo, ahí lo que se hace es un

### git fetch

y esto me lo trae al repositorio local pero no me lo copia en mis archivos, para que me lo copie en mis archivos tengo que fusionar la última versión que está en el repositorio local con mi versión actual y esto se llama un **merge**

### git merge

Pero para que tener que hacer `fetch` y `merge` al mismo tiempo si al final lo que yo quiero es que me traiga al repositorio y al directorio, tal cual como hice cuando clone el repositorio, hay un comando que fuciona dichos conceptos

### git pull

Entonces, cuando hago un `pull` lo que hago es que copio el repositorio local, la base de datos de cambios y copio el directorio de esa manera siempre tengo una copia actualizada de lo último que paso en el repositorio

[Siguiente **&#129042;**](007_Guardando_Cambios_En_Repositorio.md "Guardando cambios en el repositorio")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")


