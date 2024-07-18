---
title: Tabla de forma libre
description: Las tablas de forma libre son la base del análisis de datos en Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: ef2b452a0dcb2659b49fc0507b096952a89ea2f4
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 65%

---

# Tabla de forma libre

En Analysis Workspace, una tabla de forma libre es la base del análisis de datos interactivo. Puede arrastrar y soltar una combinación de [componentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=es) en filas y columnas para crear una tabla personalizada para su análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente, para que pueda analizar rápidamente y explorar en mayor profundidad.

## Crear una tabla de forma libre simple

Empiece con una tabla de forma libre vacía.

![Tabla de forma libre vacía](assets/freeform-table-1.png)

Si suelta la métrica **[!UICONTROL ** Visitas **]** en **[!UICONTROL ** Colocar una métrica aquí (o cualquier otro componente)**]**, la tabla de forma libre se rellenará automáticamente con visitas por día durante el período de calendario que haya seleccionado.

![Visitas a la tabla de forma libre](assets/freeform-table-2.png)

Si después suelta la dimensión **[!UICONTROL ** Página **]** para reemplazar la columna de dimensión **[!UICONTROL ** Día **]**, la tabla de forma libre reflejará automáticamente las visitas de cada página.

![Visitas por tabla de forma libre de página](assets/freeform-table-3.png)

Entonces puede desglosar, por ejemplo, la página **[!UICONTROL ** category:5 **]** soltando la dimensión **[!UICONTROL ** Canal de marketing **]** en la fila **[!UICONTROL ** category:5 **]**.

![Desglose de visitas por tabla de forma libre de página](assets/freeform-table-4.png)


## Tablas automatizadas

Como se ilustra más arriba, la forma más rápida de crear una tabla es soltar componentes directamente en un proyecto, panel o tabla de forma libre en blanco. Se creará automáticamente una tabla de forma libre en un formato recomendado. [Vea el tutorial](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=es).

![](assets/automated-table.png)

## Generador de tablas de forma libre

Si prefiere primero agregar varios componentes a la tabla y luego procesar los datos, puede habilitar el Generador de tablas de forma libre. Con el generador habilitado, puede arrastrar y soltar varias dimensiones, desgloses, métricas y segmentos para crear tablas que respondan a preguntas más complejas. Los datos no se actualizarán sobre la marcha, sino una vez que hagas clic en **[!UICONTROL Generar]**.

![](assets/table-builder.png)

## Interacciones de tabla

Puede interactuar con una tabla de forma libre y personalizarla de diversas maneras:

* **Filas**
   * Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=es) del proyecto.
   * Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Haga clic en el número junto a Filas para mostrar más filas en una página. Navegue a otra página utilizando la flecha de página en el encabezado.
   * Las filas se pueden desglosar en componentes adicionales. Para desglosar muchas filas a la vez solo tiene que seleccionar varias filas y arrastrar el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=es).
   * Las filas se pueden [filtrar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=es) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en [Configuración de fila](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=es).

* **Columnas**
   * Los componentes se pueden apilar en columnas para crear métricas segmentadas, análisis entre fichas, etcétera.
   * La vista de cada columna se ajusta en la [configuración de columna](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=es).
   * Hay varias acciones disponibles a través del [menú accesible mediante el botón secundario](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=es). El menú proporciona diferentes acciones en función de si se hace clic en el encabezado de tabla, en las filas o en las columnas.

## Exportar datos de tabla de forma libre

Obtenga más información sobre todas las [opciones de exportación](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es) de datos de Analysis Workspace.

* Al hacer clic con el botón derecho en > **[!UICONTROL Copiar datos en el portapapeles]**, se exportan los datos de tabla mostrados. Si se realiza una selección de tabla, esta opción dirá **[!UICONTROL Copiar selección al portapapeles]**. La tecla de acceso directo **Ctrl + C** también copia los datos seleccionados.
* Al hacer clic con el botón derecho en > **[!UICONTROL Descargar datos como CSV]**, se descargan los datos de tabla mostrados como CSV. Si se hace una selección de tabla, esta opción indicará **[!UICONTROL Descargar selección como CSV]**.
* Al hacer clic con el botón derecho en > **[!UICONTROL Proyecto > Descargar elementos como CSV]**, se exportan hasta 50 000 elementos de dimensión de la dimensión seleccionada.

Obtenga más información sobre todas las [opciones de exportación](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es) de datos de Analysis Workspace.

![](assets/export-options.png)

## Vídeos

Descripción general del generador de tablas de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/31318/?quality=12)

Filtros de tablas de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/23232/?quality=12)

Totales de tabla de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/29273/?quality=12)
