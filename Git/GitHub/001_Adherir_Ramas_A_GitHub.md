# Resumen

Despues de crear una rama *branch* en GitHub podemos seguir con el siguiente paso.

Para agregar un nuevo *branch* a GitHub mediante Git debemos utilizar el siguiete comando:

    git remote add origin https://github.com/amhedriel/miweb.git

## git remote
Nos sirve para que nosotros podamos indicar si es que vamos a tener un servidor remoto en el cual podemos subirnuestros cambios.

## add origin
Es que le estamos indicando de donde tenemos que obtener nuestro código y a donde tenemos que subir los cambios realizados.

## https://github.com/amhedriel/miweb.git
Este sería el url donde se encuentra almacenado nuestro código.

Ahora al volver a nuestro explorador veremos la siguiente línea de comandos a realizar

    git push -u origin main

## git push
Es el comando para que nosotros podamos subir nuestros cambios con respecto a la rama que nosotros estemos trabajando, sin embargo la rama de **main** no se encuentra creada de momento en nuestro repositorio en GitHub por lo que tenemos que indicarle que queremos crearla.

## -u

Con este comando podemos crear la rama en este caso **main**.

## origin
Indicamos que en el origen, con `origin` le indicamos en donde queremos que sea creada.

## main
Y nombramos a la rama con el nombre de **main**.

Una vez hecho estos pasos puede que nos pregunte por el Usuario y la llave Token en caso de tener que usarlo en GitHub, para eso vamos a **Settings -> Developer setings -> Personal acces tokens** Generamos un nuevo token, y debemos indicar cómo se llamará el token, luego tiempo de expiración, alcance de token y señalamos todas las opciones del repositorio, por ultimo pinchamos en **Generate token**.

Veremos el token generado y lo copiamos con la opcion de copy a su lado y lo copiaremos dentro de la Keyword en Git.

Para revisar si funciono volvemos a GitHub y revisamos en Code, actualizamos de ser necesario y veremos nuestra rama con los datos en la nube.

## Seguir agregando cambios

Ahora cada vez que queramos seguir agregando cambios, simplemente vamos a la terminal y escribimos `git add`, realizamos un `git commit -m""` y finalmente realizamos un `git push`con eso tomamos nuestros cambios y se suben.

