# Cambiar el nombre del repositorio Git

## Introducción

Si cambió el nombre del repositorio en el lado remoto, GitHub o Bitbucket, cuando pushee su código existente, verá un error: Error fatal, no se encontró el repositorio...

También funciona para cambiar el nombre del repositorio en el lado remoto que pudimos haber tenido que cambiar url, ya sea por error al hacer `fork` o solo querer cambiar url del repositorio main.

## Cambiar configuración local

Ir a terminal.

~~~bash
cd project folder
git remote -v (Para poder mirar en pantalla el anterior url de git)
git remote set-url origin https://github.com/Amhedriel/...newName.git 
git remote -v (Así veríamos el nuevo url de git)
git push (Para hacer un push de la rama)
~~~



[Siguiente **&#129042;**](/markdown/018_Estructura_Tablas.md "Resumen")

---
[*Volver* **&ldca;**](/markdown/README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")