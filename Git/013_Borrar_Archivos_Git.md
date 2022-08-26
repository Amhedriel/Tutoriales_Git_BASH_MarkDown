# Para borrar archivos RM

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



