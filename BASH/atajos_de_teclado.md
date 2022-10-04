# Atajos de teclado en BASH

## Observaciones

`bind -P` muestra todos los accesos directos configurados.

* [Atajos tipo historial](#atajos-tipo-historial)
* [Atajos de edición](#atajos-de-edición)
* [Control de trabajo](#control-de-trabajo)
* [Macros](#macros)

## **Atajos tipo historial**

ATAJO | DESCRIPCIÓN
--- | :---:
Ctrl + r | Buscar historial atrás
Ctrl + p | Comando anterior
Ctrl + n | Siguiente comando
Ctrl + g | Salir del modo de búsqueda de historial
Alt + . | Usa la última palabra del comando anterior
Alt + n Alt + . | Usa la palabra nth del comando anterior
!! + Regresar | Ejecuta el último comando otra vez: sudo !!

## **Atajos de edición**

ATAJO | DESCRIPCIÓN
--- | :---:
Ctrl + a | Ir al principio de la línea
Ctrl + e | Ir al final de la línea
Ctrl + k | Mata el texto desde la posición actual hasta el final de la línea
Ctrl + u | Mata el texto desde la posición avtaual del cursor hasta el principio de la línea
Ctrl + w | Mata la palabra detrás de la posición actual del cursos
Alt + b | Retroceder una palabra
Alt + f | Avanzar una palabra
Ctrl + Alt + e | Expandir la línea del shell
Ctrl + y | Haz retroceder el texto eliminado más recientemente en el búfer en el cursor
Alt + y | Rotar a travéz del texto eliminado. Solo SI se uso Ctrl+y o Alt+y

## **Control de trabajo**

ATAJO | DESCRIPCIÓN
--- | :---:
Ctrl + c | Detener el trabajo actual
Ctrl + z | Suspender el trabajo actual (enviar una señal SIGTSTP)

## **Macros**

ATAJO | DESCRIPCIÓN
--- | :---:
Ctrl + x , ( | Empezar a grabar una macro
Ctrl + x , ) | Dejar de grabar una macro
Ctrl + x , e | Ejecutar la última macro grabada

---
[Siguiente **&#129042;**](/BASH/Comodines.md "Comodines")

---
[*Volver* **&ldca;**](/BASH/README.md "Ir a Readme") [*Subir* **&#11165;**](# "Ir al título")