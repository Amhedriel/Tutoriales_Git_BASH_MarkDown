# Recapitulando un commit

## Master

Cada que hacemos un **commit** reemplazamos la version anterior por una nueva versión (v1, v2, v2,1 ...V actual) en la rama de Master.

---
## Development
Pero si necesitamos experimentar con distintas soluciones para luego agregar a la master y no tener complicaciones por los cambios que realizemos debemos crear otro **branch** (rama) en este caso lo llamaremos experimentos, supongamos que modoficamos la versión 2 del **commit** y seguimos experimentando hasta poder sacar la V2.1, mejorada.

---
## Hotfix o budfixing
Ahora digamos que tropezamos con un bug terrible en la **rama** de experimentación, si necesitamos arreglar un bug de la versión actual lo más probable es que debamos crear una rama "bugfixing" o en la industria actual lo llaman "hotfix", ahi hacemos los cambios y luego lo probamos con la rama actual y esa prueba, esa conexion hacia la rama actual se lo conoce como un **merge**.

---
## Merge
Que es cuando que es cuando unes las versiones de una **rama** con otra entonces estas en la V1, la V2 hiciste un **merge** y terminas con un versión final conectada entre el cambio que hiciste, y la última versión de la **rama** ***master*** actual y esta versión se llamaría la Versión final o la versión HEAD que es ahora mismo donde estan todos los cambios.

[Siguiente **&#129042;**](/Git/016_Cambio_De_nombre.md "Resumen")

---
[*Volver* **&ldca;**](README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")
