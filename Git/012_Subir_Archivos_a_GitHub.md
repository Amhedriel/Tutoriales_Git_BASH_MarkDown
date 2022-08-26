# Archivos en la nube con GitHub

## GitHub
Lo primero que tenemos que hacer es crearnos una cuenta en GitHub, es un proceso sencillo llenando nuestros datos.

Pinchamos en new repository, colocamos el nombre del Repositorio, descripción(opcional), púlico y create repository.
Despues nos mostrará varias opciones de que podemos hacer para poder tomar todo el código de nuestro repositorio y subirlo a la nube.

David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (master)
$ git remote add origin https://github.com/Amhedriel/miweb.git

David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/miweb (master)
$ git push -u origin master
info: please complete authentication in your browser...
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 4 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (20/20), 1.74 KiB | 355.00 KiB/s, done.
Total 20 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/Amhedriel/miweb/pull/new/master
remote:
To https://github.com/Amhedriel/miweb.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.