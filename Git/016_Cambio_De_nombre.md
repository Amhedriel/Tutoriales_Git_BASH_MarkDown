# Cambio de nombre con git

## Sintaxis
*     git mv <sorce> <destination>
*     git mv - f <sorce> <destination>

## Parámetros

`-f` o ``--force``, forzará el cambio de nombre o el movimiento de un archivo.

---

## Renombrar carpetas

    git mv directoryToFolder/oldName directoryToFolder/newName

Seguido por `git commit` y/o `gui push`

Si tiene error:

    fatal: no se pudo cambiar...

Usar:

    git mv directoryToFolder/oldName temp && git mv temp directoryToFolder/newName

---

## Renombrar una rama local

Se puede cambiar el nombre de la rama en el repositorio local usando este comando:

    git branch -m old_ame new_name

---

## Renombrar una rama local y la remota

La forma más facil es tener la rama local registrada:

    git checkout old_branch

A continuación, cambie el nombre de la rama local, elimine el control remoto antiguo y establezca la nueva rama con el nuevo nombre como ascendente:

~~~bash
git branch -m new_branch
git push origin :old_branch
git push --set-upstream origin new_branch
~~~

[Siguiente **&#129042;**](/Git/017_Cambio_De_Nombre_Repositorio.md "Resumen")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")

