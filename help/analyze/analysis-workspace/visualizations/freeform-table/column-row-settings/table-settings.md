---
description: Aprenda a utilizar la configuración de fila y a variar la configuración de fila en función del componente que haya arrastrado a una tabla de forma libre en Analysis Workspace.
title: Configuración de filas
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 96%

---


# Configuración de filas


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuración de fila y columna en una tabla de forma libre](https://video.tv.adobe.com/v/328505/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

La configuración de filas varía en función del componente que haya arrastrado a la tabla. Para acceder a la configuración de las filas de la tabla, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Configuración]** junto a una dimensión, un filtro, una métrica, un periodo de tiempo o un desglose dentro de cada uno de estos objetos.

![Tabla de forma libre que resalta el icono Configuración para Métricas](assets/row-settings.png)

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Desglose por posición]** | De forma predeterminada, esta configuración está deshabilitada y los desgloses se corrigen a elementos de fila estáticos. Por ejemplo, supongamos que desglosa los 3 elementos de dimensión de página principales (página principal, resultados de búsqueda, cierre de compra) por canal de marketing. Después abandona el proyecto y regresa dos semanas más tarde. Al volver a abrir el proyecto, las 3 páginas principales han cambiado, y ahora la página principal, los resultados de búsqueda y el cierre de compra son las 4 o 6 páginas principales. De forma predeterminada, los desgloses del canal de marketing siguen apareciendo en la página principal, los resultados de búsqueda y el cierre de compra, aunque ahora se encuentren en las filas 4-6. <br> Por el contrario, **Desglose por posición** siempre desglosará los tres elementos principales, independientemente de cuáles sean. En referencia al ejemplo anterior, cuando vuelva a abrir el proyecto, los desgloses de canal de marketing se vinculan a las 3 páginas principales de la tabla. Y no a la página principal, los resultados de búsqueda y el cierre de compra, que ahora están en las filas 4-6. |
| **[!UICONTROL Porcentajes]** | **Calcular porcentajes por columna** (por defecto): los porcentajes visibles en las celdas se calculan en función del total de la columna. <br>**Calcular porcentajes por fila**: los porcentajes de las celdas se calculan a lo largo de la fila, en lugar de a lo largo de la columna, con el total general como denominador. Este cálculo resulta útil en los porcentajes de tendencias. |
| **[!UICONTROL Totales de columna]** | Esta configuración solo está disponible para [filas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostrar como suma de las filas actuales** muestra una suma del lado del cliente de las filas de la tabla, lo que significa que el total *no* desduplica métricas como las visitas o las personas. <br> **Mostrar total general** muestra una suma del lado del servidor, es decir, el total de las métricas deduplicadas. |

## Cambio del recuento de filas

Para cambiar el número de filas que se muestran:

1. Haga clic en el número que aparece junto a **[!UICONTROL Filas]** en la parte superior de la primera columna de la tabla.

   ![Tabla de forma libre que muestra la lista desplegable de para el número de filas mostradas. Se ha seleccionado 400 filas.](assets/change-row-count.gif)

1. En la lista desplegable, seleccione el número de filas que desee que muestre la tabla.


## Menú contextual

Las siguientes opciones de menú contextual están disponibles al seleccionar el encabezado de la dimensión.

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Copiar selección al portapapeles]** | Copia la selección de la visualización en el portapapeles. |
| **[!UICONTROL Descargar elementos como CSV (*nombre de dimensión*)]** | Descarga inmediatamente los elementos de dimensión (hasta un máximo de 50 000) de la visualización en su dispositivo local. Un máximo de 50 000 elementos de dimensión para la dimensión seleccionada. |
| **[!UICONTROL Descargar selección como CSV]** | Descargue inmediatamente los elementos de dimensión de la visualización en su dispositivo local. |
| **[!UICONTROL Crear hipervínculos para todos los elementos de dimensión]** | Cree hipervínculos para todos los elementos de dimensión. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hipervínculos para todos los elementos de dimensión]** | Editar hipervínculos para todos los elementos de dimensión. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Quitar hipervínculos de todos los elementos de dimensión]** | Quite hipervínculos de todos los elementos de dimensión. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Eliminar]** | Elimina la dimensión de la tabla. |
| **[!UICONTROL Visualizar]** | Visualice la dimensión con cualquiera de las visualizaciones disponibles. |
| **[!UICONTROL Mostrar solamente las filas seleccionadas]** | Muestre solo los elementos seleccionados en la visualización. |
| **[!UICONTROL Crear anotación a partir de la selección]** | Abra **[!UICONTROL Detalles de anotación]** para añadir una anotación. |


Las siguientes opciones de menú contextual adicionales están disponibles al seleccionar uno o más elementos de dimensión (primera columna) o una o más celdas individuales en la tabla de forma libre.

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Crear hipervínculo]** | Cree un hipervínculo para el elemento. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hipervínculo]** | Edite un hipervínculo para el elemento. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Quitar hipervínculo]** | Quite un hipervínculo para el elemento. Consulte [Hipervínculos para dimensiones en una tabla de forma libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Desglose]** | Desglose del elemento de dimensión. Seleccione de la lista de **[!UICONTROL dimensiones]**, **[!UICONTROL métricas]**, **[!UICONTROL filtros]** o **[!UICONTROL intervalos de fechas]**. Búsqueda alternativa para un componente, usando *Buscar*. |
| **[!UICONTROL Eliminar selección]** | Eliminar las filas seleccionadas (elementos). |
| **[!UICONTROL Selección de tendencia]** | Cree una visualización de gráfico de líneas de tendencias para la selección. |
| **[!UICONTROL Mostrar solamente las filas seleccionadas]** | Mostrar solo las filas seleccionadas en la visualización. |
| **[!UICONTROL Mostrar todas las filas]** | Mostrar todas las filas de la visualización. |
| **[!UICONTROL Crear filtro a partir de la selección]** | Abra **[!UICONTROL Generador de filtros]** para generar un filtro a partir de la selección. |
| **[!UICONTROL Crear audiencia a partir de la selección]** | Abra el cuadro de diálogo **[!UICONTROL Crear audiencia]** para generar una audiencia a partir de la selección. |

Las siguientes opciones de menú contextual adicionales están disponibles al seleccionar un encabezado de columna de métrica.

| Opción | Descripción |
|---|---|
| **[!UICONTROL Crear métrica a partir de la selección]** | Cree una nueva métrica a partir de la métrica seleccionada. La métrica puede ser Media, Mediana, Máx. columna, Mín. columna, Suma columna. También puede seleccionar Abrir en el creador de métricas calculadas para crear una métrica calculada. |
| **[!UICONTROL Añadir columna de período de tiempo]** | Añadir una columna de periodo de tiempo. Se le ofrecen varias opciones, donde el intervalo de calendario del panel determina el *intervalo de fechas*: <li>**[!UICONTROL *Intervalo de fechas* anterior a este intervalo de fechas]**</li><li>**[!UICONTROL Estos *intervalos de fechas* a este intervalo de fechas]**.</li><li>**[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**. Abre el **[!UICONTROL Generador de intervalos de fechas]** para especificar el intervalo de fechas.</li>Consulte [Comparación de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md) para obtener más información. |
| **[!UICONTROL Comparar períodos de tiempo]** | Añade columnas de período de tiempo de comparación. Solo está disponible cuando la dimensión no está basada en el tiempo. Se le ofrecen varias opciones para determinar el *intervalo de fechas*: <li>**[!UICONTROL *Intervalo de fechas* anterior a este intervalo de fechas]**</li><li>**[!UICONTROL Intervalo de fechas personalizado a este intervalo de fechas]**. Abre el **[!UICONTROL Generador de intervalos de fechas]** para especificar el intervalo de fechas.</li>Consulte [Comparación de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md) para obtener más información. |
| **[!UICONTROL Modificar modelos de atribución]** | Modifique el modelo de atribución para la columna. |
| **[!UICONTROL Comparar modelo de atribución]** | Especifique un nuevo modelo de atribución y compárelo con el modelo de atribución de la columna seleccionada. Se añade una nueva columna con las nuevas métricas del modelo de atribución. Además, se añade una columna Cambio porcentual para la comparación. |
| **[!UICONTROL Restablecer anchos de columna]** | Restablezca el ancho de columna predeterminado. |
| **[!UICONTROL Crear anotación a partir de la selección]** | Abra **[!UICONTROL Detalles de anotación]** para añadir una anotación. |
| **[!UICONTROL Crear filtro a partir de la selección]** | Abra **[!UICONTROL Generador de filtros]** para generar un filtro a partir de la selección. |
| **[!UICONTROL Crear audiencia a partir de la selección]** | Abra el cuadro de diálogo **[!UICONTROL Crear audiencia]** para generar una audiencia a partir de la selección. |

## Cambiar altura de fila

Puede establecer la [densidad de visualización](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) de un proyecto en **[!UICONTROL Compacto]**, **[!UICONTROL Cómodo]** y **[!UICONTROL Expandido]**.
