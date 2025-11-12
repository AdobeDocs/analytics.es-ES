---
description: Ejemplos, notas y notas sobre sintaxis acerca del uso de intervalos de fechas en expresiones personalizadas.
title: Ejemplos de intervalos de fechas utilizando expresiones personalizadas
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 14%

---

# Ejemplos de intervalos de fechas utilizando expresiones personalizadas

{{legacy-arb}}

Ejemplos, notas y notas sobre sintaxis acerca del uso de intervalos de fechas en expresiones personalizadas.

En la tabla se supone que la fecha de hoy es lunes, 10 de noviembre de 2011, utilizando el calendario gregoriano.

| Ejemplo | Intervalo de fechas | Personalizar expresión | Intervalo de fechas del informe |
|---|---|---|---|
|  | | **De** | **Hasta** |
| 1 | Hace dos semanas | `cw-2w  \| cw-1w-1d` | 26 de octubre a 1 de noviembre |
| 2 | Primeros 3 días del quinto mes del año pasado | `cy-1y+4m  \| cy-1y+4m+2d` | 1 a 3 de mayo de 2010 |
| 3 | Una semana completa, a partir de hace 4 semanas | `cw-4w  \| cw-3w-1d` | 12 a 18 de octubre |
| 4 | Última semana del año anterior | `cw-53w  \| cw-52w-1d` | 9 de noviembre de 2010 |
| 5 | Un mes a partir de hace dos meses | `cm-2m  \| cm-1m-1d` | 1 a 30 de septiembre |
| 6 | Hace 12 meses en el año anterior | `cm-12m  \| cm-11m-1d` | 1 a 30 de noviembre de 2010 |

## Notas sobre los ejemplos {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Ejemplo 1**

Si hoy es lunes, 10 de noviembre de 2011, tome la fecha actual y reste una semana para obtener la última semana completa de octubre.

**Ejemplo 2**

Agregue cuatro meses al comienzo del año (el mes de enero) para obtener el mes de mayo; agregue dos días al primer día del mes para obtener el tercer día del mes.

## Notas de sintaxis {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Se pueden crear expresiones personalizadas que abarquen la mayoría de los intervalos de fechas vinculando dos términos con un operador. Un término es una combinación de un multiplicador entero y una abreviatura de punto. Un ejemplo de término es 18d. Un ejemplo de operador es +.

* No se permiten espacios en blanco entre operadores y términos.
* Utilice solo estas abreviaturas: cd cw cm cq cy d w m q y
* Se recomienda utilizar la misma referencia de fecha en la fecha de inicio y en la fecha de finalización: cd, cd o cw, cw o cy, cy. La combinación de referencias de fechas puede llevar a fechas no válidas en determinadas épocas del año.
* Los múltiplos válidos de las abreviaturas d w m q y se forman mediante enteros ( 1 2 3 ... ) antepuestos a la abreviatura, como 53d 3w 5q 9m 2y
* No se permiten números no enteros.
* No anteponga solo un cero a la abreviatura. Por ejemplo, no se permite 0w.
* Se utilizan los siguientes operadores para concatenar abreviaturas: + -
* Dado que los intervalos de fechas deben calcularse en relación con el periodo actual, el primer término de una expresión siempre comienza por c.
