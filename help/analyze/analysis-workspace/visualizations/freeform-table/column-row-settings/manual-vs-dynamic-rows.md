---
title: Elementos De Dimension Dinámicos Y Estáticos
description: Aprenda a utilizar elementos de dimensión dinámicos frente a estáticos en tablas de forma libre en Analysis Workspace.
feature: Freeform Tables
role: User, Admin
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
TQID: https://experienceleague.adobe.com/hP5X4gRBiRB1wmGziYT25iGS-Enpuu0C--3qeGxrvb4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 576
ht-degree: 80%

---

# Elementos de dimensión dinámicos y estáticos

En las tablas improvisadas, las filas y columnas pueden contener varios valores de componente. Estos valores pueden ser dinámicos (cambian con el tiempo) o estáticos (no cambian con el tiempo), según el análisis que desee generar.

## Elementos de dimensión dinámicos

Los elementos de dimensión dinámicos cambian con el tiempo y dependen de la métrica por la que se ordena en la tabla de forma libre. Se prefieren los elementos de dimensión dinámicos cuando desea analizar los elementos principales de un período de tiempo determinado.

Cuando se coloca una dimensión en una tabla de forma libre, se devuelven filas dinámicas. Las filas dinámicas representan los elementos principales que corresponden a la dimensión de una métrica y un período de tiempo determinados. También puede colocar una dimensión en columnas de tabla de forma libre y esta se expande automáticamente a los 5 elementos de dimensión principales.

Por ejemplo, cuando arrastra la dimensión Tipo de explorador a la tabla, los elementos de dimensión Tipo de explorador principales (por ejemplo, Microsoft, Apple, Google, etc.) volver dinámicamente a las filas de la tabla. Si se sueltan en una columna, los 5 elementos de dimensión Tipo de explorador principales se devuelven de forma dinámica.

Los elementos de dimensión dinámicos tienen la opción de filtro de fila ![Filter](/help/assets/icons/Filter.svg) y ![Close](/help/assets/icons/Close.svg), y **not** tienen un bloqueo ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Al hacer clic en ![Cerrar](/help/assets/icons/Close.svg) junto a un elemento de dimensión dinámica, se aplica automáticamente un filtro. Para obtener más información sobre cómo aplicar filtros a las tablas, consulte [Filtrar y ordenar tablas](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Una tabla de forma libre que resalta el icono de filtro.](assets/dynamic-items.png)

## Elementos de dimensión estáticos

Los elementos de dimensión estáticos no cambian con el tiempo; son componentes fijos que siempre se devuelven en una tabla de forma libre. Se prefieren los elementos de dimensión estáticos cuando se desea analizar siempre el mismo elemento, ya sean campañas específicas o días específicos de la semana.

Cada vez que selecciona y suelta manualmente valores de componente específicos (dimensión, métrica, filtro, intervalo de fechas) en una tabla, el resultado es una lista estática de filas o columnas.

Por ejemplo, cuando arrastra elementos específicos de Tipo de explorador como Microsoft y Apple, esos dos elementos específicos siempre se arrastran a la tabla.

También se pueden crear elementos de dimensión estáticos si elige seleccionar **[!UICONTROL Mostrar solo las filas seleccionadas]** en el menú contextual para las filas seleccionadas.

Los elementos de dimensión estáticos **no** tienen la opción de filtro de fila. En su lugar, aparecen un ![BloqueoCerrado](/help/assets/icons/LockClosed.svg) y un ![Cerrar](/help/assets/icons/Close.svg) en cada elemento. Seleccione ![Cerrar](/help/assets/icons/Close.svg) para eliminar ese elemento de dimensión de la tabla.

![Una tabla de forma libre que muestra el tipo de explorador y la fila de Microsoft con un icono de candado. Nota: este elemento de dimensión es estático y no cambiará con el tiempo.](assets/static-items.png)

## Elementos de dimensión mixtos

Los elementos de dimensión de diferentes dimensiones se pueden agregar a la misma tabla. En estos casos, el encabezado de fila indica **[!UICONTROL Dimensiones mixtas]**. Estos elementos de dimensión son estáticos. Por ejemplo, si añade elementos de dimensión específicos desde la dimensión Grupo del explorador y otros elementos de dimensión desde la dimensión Nombre del explorador.

![Una tabla de forma libre que resalta la columna Dimensiones mixtas.](assets/mixed-dimensions.png)

## Filas totales improvisadas

Las filas dinámicas y estáticas se comportan de forma diferente en la fila total improvisada. De forma predeterminada:

* Las filas dinámicas se suman a las métricas del lado del servidor y a las duplicadas, como sesiones o personas.
* Las filas estáticas se suman al lado del cliente y **no** eliminan las métricas duplicadas. Para calcular el total de filas del lado del servidor, cambie la configuración fila a **Mostrar total general**. [Más información](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Reordenar filas estáticas](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/reordering-static-rows-in-analysis-workspace){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


