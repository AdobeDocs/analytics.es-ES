---
description: Ejemplos, notas y notas sobre sintaxis acerca del uso de intervalos de fechas en expresiones personalizadas.
title: Ejemplos de intervalos de fechas utilizando expresiones personalizadas
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 99%

---


# Ejemplos de intervalos de fechas utilizando expresiones personalizadas

Ejemplos, notas y notas sobre sintaxis acerca del uso de intervalos de fechas en expresiones personalizadas.

En la tabla se asume que la fecha de hoy es Lunes, 10 de noviembre de 2011, utilizando el calendario gregoriano.

| Ejemplo | Intervalo de fechas | Expresión personalizada | Intervalo de fechas del informe |
|---|---|---|---|
|  |  | **De** | **Hasta** |  |
| 1 | Hace dos semanas | cw-2w | cw-1w-1d | 26 de octubre a 1 de noviembre |
| 2 | Primeros 3 días del quinto mes del año pasado | cy-1y+4m | cy-1y+4m+2d | 1 a 3 de mayo de 2010 |
| 3 | 1 semana completa, comenzando 4 semanas antes | cw-4w | cw-3w-1d | 12 a 18 de octubre |
| 4 | Última semana del año anterior | cw-53w | cw-52w-1d | de noviembre a 9 de noviembre de 2010 |
| 5 | 1 mes, comenzando 2 meses antes | cm-2m | cm-1m-1d | 1 a 30 de septiembre |
| 6 | 12 meses antes en el año anterior | cm-12m | cm-11m-1d | 1 a 30 de noviembre de 2010 |

## Notas sobre los ejemplos {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Ejemplo 1**

Si hoy es lunes 10 de noviembre de 2011, considere la fecha actual y reste una semana para obtener la última semana completa de octubre.

**Ejemplo 2**

Añada cuatro meses al comienzo del año (el mes de enero) para obtener el mes de mayo; añada dos días al primer día del mes para obtener el tercer día del mes.

## Notas sobre sintaxis {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Las expresiones personalizadas que abarcan la mayoría de intervalos de fechas se pueden crear vinculando dos términos con un operador. Un término es una combinación de un multiplicador entero y una abreviación de período. Un ejemplo de un término es 18d; un ejemplo de operador es +.

* No se permiten espacios en blanco entre operadores y términos.
* Utilice solo las siguientes abreviaturas: cd cw cm cq cy d w m q y
* La práctica recomendada es usar la misma referencia de fecha en la fecha de inicio y en la de finalización: cd, cd o cw; cw o cy; cy. La mezcla de referencias de fecha puede implicar fechas no válidas en determinados momentos del año.
* Los múltiplos válidos de las abreviaciones d w m q y se forman mediante enteros ( 1, 2, 3...) antepuestos a la abreviación del modo siguiente 53d 3w 5q 9m 2y
* No se permiten números que no sean enteros.
* No anteponga la abreviación con solo un cero. Por ejemplo, 0w no se permite.
* Los siguientes operadores se utilizan para concatenar abreviaciones: + -
* Debido a que los intervalos de fechas deben calcularse en función del período actual, el primer término de una expresión siempre comienza por c.

