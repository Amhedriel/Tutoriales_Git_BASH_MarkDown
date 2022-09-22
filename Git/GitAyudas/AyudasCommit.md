# Algo de info extra

## **¿Cómo cambiar el mensaje de un commit?**

Acabo de hacer un commit:

    git commit -m "este es un comentario"

Sin embargo, de repente me he dado cuenta de que este mensaje no es el correcto. ¿Puedo modificarlo?

**Si sí, ¿cómo?**

Si vuelvo a escribir 

    git commit -m "un nuevo comentario" 

***hará otro commit*** en lugar de modificar el que ya hice.

---

>La opción más práctica y rápida es usar:

    git commit --amend

Tras lo cual se te abrirá el editor para que puedas modificar el mensaje.

Si quieres escribir algo totalmente nuevo, puedes decir directamente:

    git commit --amend -m "Este es el nuevo comentario"

Puedes ver más detalles en la respuesta en la versión inglesa a Edit an incorrect commit message in Git.

---

También puedes editar el histórico de commits para modificar mas de un mensaje, usando git rebase

    git rebase -i HEAD~2

Esto te abrira un editor de texto (vim) donde puedes actualizar los mensajes del histórico de commits.

En realidad, ahí no se modifican directamente los mensajes, para hacerlos hay que cambiar la acción por **"reword"** lo cual después permite modificar el mensaje

__________________________________
---

## Errores

Un error que me sale muy seguido, y al parecer es por modificar archivos directamente en **GitPush** y no en mi IDE.

~~~bash
$ git push
To https://github.com/Amhedriel/HTML_Tutorial.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/Amhedriel/HTML_Tutorial.g
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
~~~

Una solución:

### **git-pull**

``git-pull`` - Obtener e integrar con otro repositorio o una sucursal local.

    git pull [<options>] [<repository> [<refspec>…​]]

Incorpora los cambios de un repositorio remoto a la rama actual. Si la rama actual está detrás del control remoto, de forma predeterminada adelantará rápidamente la rama actual para que coincida con el control remoto. Si la rama actual y el control remoto han divergido, el usuario debe especificar cómo conciliar las ramas divergentes con o (o la opción de configuración correspondiente en ).``--rebase--no-rebasepull.rebase``

Más precisamente, se ejecuta con los parámetros dados y luego, dependiendo de las opciones de configuración o los indicadores de línea de comandos, llamará a cualquiera de los dos o para reconciliar ramas divergentes.``git pullgit fetchgit rebasegit merge``.

<repository> debe ser el nombre de un repositorio remoto como se pasa a git-fetch(1). <refspec> puede nombrar una referencia remota arbitraria (por ejemplo, el nombre de una etiqueta) o incluso una colección de referencias con las ramas de seguimiento remoto correspondientes (por ejemplo, refs/heads/*:refs/remotes/origin/*), pero generalmente es el nombre de una rama en el repositorio remoto.

Los valores predeterminados para <repository> y <branch> se leen desde la configuración "remote" y "merge" para la rama actual según lo establecido por git-branch(1) .--track

Supongamos que existe el siguiente historial y que la rama actual es "":master

          A---B---C master on origin
         /
    D---E---F---G master
        ^
        origin/master in your repository
Luego, "" buscará y reproducirá los cambios de la rama remota desde que divergió de la local (es decir, ) hasta su confirmación actual () además de y registrará el resultado en una nueva confirmación junto con los nombres de las dos confirmaciones principales y un mensaje de registro del usuario que describe los cambios.git pullmastermasterECmaster

          A---B---C origin/master
         /         \
    D---E---F---G---H master
Consulte git-merge(1) para obtener más información, incluida la forma en que se presentan y tratan los conflictos.

En Git 1.7.0 o posterior, para cancelar una combinación en conflicto, use . Advertencia: En versiones anteriores de Git, se desaconseja ejecutar git pull con cambios no comprometidos: si bien es posible, te deja en un estado del que puede ser difícil retirarse en caso de conflicto.git reset --merge

Si alguno de los cambios remotos se superpone con los cambios locales no confirmados, la combinación se cancelará automáticamente y el árbol de trabajo no se tocará. En general, es mejor obtener cualquier cambio local en el estado de funcionamiento antes de tirarlos o guardarlos con git-stash(1).

Para recibir ayuda rápìda.

    $ git pull -h

Ahora bién el comando sería:

    $ git pull origin master

Dónde `master` es la rama actual, suele ser `main`. Una vez realizado el comando pararecerá algo como esto:

~~~bash
David@Ciri MINGW64 ~/HTML (master)
$ git pull origin master
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (2/2), done.
remote: Total 6 (delta 2), reused 2 (delta 2), pack-reused 4
Unpacking objects: 100% (6/6), 1.51 KiB | 8.00 KiB/s, done.
From https://github.com/Amhedriel/HTML_Tutorial
 * branch            master     -> FETCH_HEAD
   30b01b5..e593075  master     -> origin/master
Merge made by the 'ort' strategy.
 README.md | 3 +++
 1 file changed, 3 insertions(+)
~~~

Si lo revisamos con `git status`

~~~bash
David@Ciri MINGW64 ~/HTML (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

~~~

Entonces tecleamos:

    $ git push -u origin master

Que mostrará:

~~~bash
$ git push -u origin master
Enumerating objects: 18, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 4 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (10/10), 24.17 KiB | 6.04 MiB/s, done.
Total 10 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), completed with 3 local objects.
To https://github.com/Amhedriel/HTML_Tutorial.git
   e593075..e1a79e9  master -> master
branch 'master' set up to track 'origin/master'.
~~~

Y con eso deberíamos haber reparado el problema.
