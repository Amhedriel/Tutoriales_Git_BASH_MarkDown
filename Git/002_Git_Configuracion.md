# Configurar Git para enpezar a trabajar

## Versión
Primero veamos la version en la que estamos introduciendo este comando en el Git-Bash:
~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ git --version
git version 2.37.1.windows.1
~~~
Con este resultado podemos comprobar si tenemos Git  *instalado* de manera correcta.

---
## Ver donde estàn las configuraciones guardadas (Advanced)

~~~
$ git config --list --show-origin
file:C:/Program Files/Git/etc/gitconfig diff.astextplain.textconv=astextplain
file:C:/Program Files/Git/etc/gitconfig filter.lfs.clean=git-lfs clean -- %f
file:C:/Program Files/Git/etc/gitconfig filter.lfs.smudge=git-lfs smudge -- %f
file:C:/Program Files/Git/etc/gitconfig filter.lfs.process=git-lfs filter-process
file:C:/Program Files/Git/etc/gitconfig filter.lfs.required=true
file:C:/Program Files/Git/etc/gitconfig http.sslbackend=openssl
file:C:/Program Files/Git/etc/gitconfig http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
file:C:/Program Files/Git/etc/gitconfig core.autocrlf=true
file:C:/Program Files/Git/etc/gitconfig core.fscache=true
file:C:/Program Files/Git/etc/gitconfig core.symlinks=false
file:C:/Program Files/Git/etc/gitconfig pull.rebase=false
file:C:/Program Files/Git/etc/gitconfig credential.helper=manager-core
file:C:/Program Files/Git/etc/gitconfig credential.https://dev.azure.com.usehttppath=true
file:C:/Program Files/Git/etc/gitconfig init.defaultbranch=master
file:C:/Users/David/.gitconfig  filter.lfs.required=true
file:C:/Users/David/.gitconfig  filter.lfs.clean=git-lfs clean -- %f
file:C:/Users/David/.gitconfig  filter.lfs.smudge=git-lfs smudge -- %f
file:C:/Users/David/.gitconfig  filter.lfs.process=git-lfs filter-process
file:C:/Users/David/.gitconfig  user.name=David Amhed Beltrán Rubín de Celis
file:C:/Users/David/.gitconfig  user.email=davikin_01@hotmail.com
file:C:/Users/David/.gitconfig  core.editor="C:\Users\David\AppData\Local\Programs\Microsoft VS Code\bin\code" --wait
file:C:/Users/David/.gitconfig  core.autocrlf=true
file:.git/config        core.repositoryformatversion=0
file:.git/config        core.filemode=false
file:.git/config        core.bare=false
file:.git/config        core.logallrefupdates=true
file:.git/config        core.symlinks=false
file:.git/config        core.ignorecase=true
~~~
---
## Registro de nombre
Continuando con la configuracion debemos escribir:
~~~
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ git config --global user.name "David Amhed Beltrán Rubín de Celis"
~~~
La opción de `global` sirve para que la configuración que agreguemos se efectue de manera **global y no por proyecto**.
Con esto completamos el registro de nuestro nombre.

---
## Ahora configuraremos nuestro correo

~~~
$ git config --global user.email "davikin_01@hotmail.com"
~~~
Y con esto terminamos la configuracion inicial.

___
___

## Configurar el editor de texto
Le diremos a Git que nuestro editor de texto es Visal Studio Code:

    $ git config --global core.editor "code --wait"

La opción de `--wait` es para que la terminal se quede esperando hasta que cerremos nuestro editor de texto.

Si quisieramos ver nuestro archivo de configuración global tenemos que hacerlo con la siguiente instrucción:

    $ git config --global -e

Y presionamos *enter* podremos ver nuestro archivo de configuracion global dentro de VSCode

~~~
[filter "lfs"]
	required = true
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
[user]
	name = David Amhed Beltrán Rubín de Celis
	email = davikin_01@hotmail.com
[core]
	editor = code --wait
~~~

Aqui veremos nuestro nombre, el email, con que rama vamos a trabajar inicialmente y el comando con el que se utiliza para ver nuestro editor.
Mientras tanto en nuestro Bash
~~~
$ git config --global -e
hint: Waiting for your editor to close the file... 
~~~
Nos indica que está esperando a que nuestro editor se cierre.

---
## core.autocrlf
En Windows cada vez que agregamos un salto de línea Windows agregará 2 caracteres especiales para poder marcar esa línea, (Carriage Return o CR, y también Line Feed o LF). En windows para poder subir nuestro código debemos eliminar necesariamente el caracter especial de CR, pero, si lo que queremos es descargar código del repositorio debemos agregar el caracter de CR, para eso cambiaremos la configuración de Git.
Por lo que la propiedad de `core.autocrlf` tiene que tener el valor de `true` sin embargo si se está trabajando ya sea con MAC o LINUX el valor sería de `input`:

    $ git config --global core.autocrlf true

Y con esto damos por concluida la configuración de Git.

**Nota**: si quieres ahondar más en la configuración de Git puedes introducir:

    $ git config -h
Este comando nos dará un listado de todas las configuraciones con las que podemos interactuar

```Bash
David@Ciri MINGW64 ~/Dropbox/VisualStudioCode/Markdown
$ git config -h
usage: git config [<options>]

Config file location
    --global              use global config file
    --system              use system config file
    --local               use repository config file
    --worktree            use per-worktree config file
    -f, --file <file>     use given config file
    --blob <blob-id>      read config from given blob object

Action
    --get                 get value: name [value-pattern]
    --get-all             get all values: key [value-pattern]
    --get-regexp          get values for regexp: name-regex [value-pattern]
    --get-urlmatch        get value specific for the URL: section[.var] URL
    --replace-all         replace all matching variables: name value [value-pattern]
    --add                 add a new variable: name value
    --unset               remove a variable: name [value-pattern]
    --unset-all           remove all matches: name [value-pattern]
    --rename-section      rename section: old-name new-name
    --remove-section      remove a section: name
    -l, --list            list all
    --fixed-value         use string equality when comparing values to 'value-pattern'
    -e, --edit            open an editor
    --get-color           find the color configured: slot [default]
    --get-colorbool       find the color setting: slot [stdout-is-tty]

Type
    -t, --type <type>     value is given this type
    --bool                value is "true" or "false"
    --int                 value is decimal number
    --bool-or-int         value is --bool or --int
    --bool-or-str         value is --bool or string
    --path                value is a path (file or directory name)
    --expiry-date         value is an expiry date

Other
    -z, --null            terminate values with NUL byte
    --name-only           show variable names only
    --includes            respect include directives on lookup
    --show-origin         show origin of config (file, standard input, blob, command line)
    --show-scope          show scope of config (worktree, local, global, system, command)
    --default <value>     with --get, use default value when missing entry
```
[Siguiente **&#129042;**](003_Git_Ayuda.md "¿Cómo obtener ayuda?")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")


