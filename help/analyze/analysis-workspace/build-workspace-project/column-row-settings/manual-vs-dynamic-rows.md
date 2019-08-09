---
description: Cómo interactuar con filas estáticas en tablas.
seo-description: Cómo interactuar con filas estáticas en tablas.
seo-title: Filas estáticas o dinámicas
title: Filas estáticas o dinámicas
uuid: caf 033 ef-d 252-4 f 8 a -802 e -7 edbbac 5 c 8 c 0 c
translation-type: tm+mt
source-git-commit: a121851d3f96aee243aaffd2fde24c98d4fc55e1

---


# Filas estáticas o dinámicas

Las tablas de Analysis Workspace generan filas “dinámicas” al soltar una dimensión en una tabla. Esto significa que todos los elementos que corresponden a esa dimensión, para una métrica dada, se arrastran a la tabla.

Por ejemplo, si arrastra la dimensión Explorador hasta una tabla, todos los elementos de su dimensión (p. ej. el explorador de Android, Mobile Safari, Firefox, etc.) se arrastran a la tabla de forma dinámica.

Por el contrario, cada vez que seleccione y suelte manualmente un elemento específico de métrica, segmento, intervalo de fechas o dimensión individual en una tabla, el resultado es una fila o lista por defecto o “manual”. Puede interactuar con una fila estática de las siguientes formas:

* Haga clic en el icono Previsualización en las filas estáticas para previsualizar los segmentos, métricas e intervalos de fechas.
* Haga clic en el icono “x” para eliminar dicha fila de la tabla.
* Limite cuántas filas desea mostrar y habilite la paginación.
* Añada “elementos de dimensión mixtos”. Por ejemplo, añada un elemento de una dimensión de explorador y otro elemento de una dimensión de producto.

   A continuación verá una ilustración:

   ![](assets/static_rows.png)

Además, (solo) cuando se encuentra en un modo de fila estática, ahora puede cambiar cómo se calculan los totales de columnas. Solo tiene que hacer clic en el icono de engranaje y alternar entre estas dos opciones:

![](assets/column-totals.png)

| Opción | Descripción |
|---|---|
| (Predeterminado) Calcule los totales sumando los valores actualmente en cada columna. | Esta opción solo calcula las filas actuales de la tabla (cálculo del lado del cliente). |
| Calcular los totales basados en todas las filas para cada métrica. | Esta opción incluye todos los elementos de dimensión para dicha dimensión, incluso los que no aparecen en la lista (cálculo del lado del servidor). |

