---
title: Tabla improvisada
description: Obtenga información sobre las tablas improvisadas y el generador de tablas improvisadas
translation-type: tm+mt
source-git-commit: b952ea84a63cdb73684e8765dde6551785c0d6c1
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 95%

---


# Tabla improvisada

En Analysis Workspace, una tabla improvisada no es solamente una tabla de datos, sino también una visualización interactiva. Puede arrastrar y soltar una combinación de [componentes](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) en las filas y columnas para crear una tabla personalizada para el análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda realizar un análisis rápido.

Puede personalizar la tabla de varias formas:

* **Filas**
   * Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) del proyecto.
   * Las filas se pueden desglosar en componentes adicionales. Para desglosar muchas filas a la vez solo tiene que seleccionar varias filas y arrastrar el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Las filas se pueden [filtrar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en [Configuración de fila](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html).

* **Columnas**
   * Los componentes se pueden apilar en columnas para crear métricas segmentadas, análisis entre fichas, etcétera.
   * La vista de cada columna se ajusta en la [configuración de columna](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Hay varias acciones disponibles a través del [menú accesible mediante el botón secundario](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). El menú proporciona diferentes acciones en función de si se hace clic en el encabezado de tabla, en las filas o en las columnas.

## Generador de tablas improvisadas

Si prefiere primero agregar varios componentes a la tabla y luego procesar los datos, puede habilitar el Generador de tablas improvisadas. Con el Generador de tablas improvisadas, puede arrastrar y soltar varias dimensiones, desgloses, métricas y segmentos para crear tablas que respondan a preguntas más complejas. Los datos no se actualizarán sobre la marcha, sino una vez que haga clic en **[!UICONTROL Generar]**.

El Generador de tablas es una opción que ahorra tiempo cuando tiene una pregunta compleja que hacer sobre los datos y tiene una idea de qué tabla desea crear para responder a su pregunta. Otras ventajas del generador de tablas incluyen la capacidad de:

* Organizar la tabla en el formato que necesite, sin tener que esperar a que se procese cada acción.
* Realizar rápidamente hasta 4 niveles de desgloses.
* Definir la configuración de Fila y Desglose para cada fila de tabla y columna de dimensión.
* **[!UICONTROL Desglose por posición]** para cada nivel de la tabla de forma predeterminada (en las tablas improvisadas tradicionales, el valor predeterminado es **[!UICONTROL Desglosar por elemento]**).
* Ordenar manualmente filas estáticas en la tabla. Por ejemplo, si desea que las filas de métricas aparezcan en un orden determinado.
* Previsualizar el formato de la tabla antes de procesar datos reales.

Observe cómo funciona el Generador de tablas improvisadas [aquí](https://youtu.be/GUMWiJAmMGI).

## Exportar datos de tabla improvisada

Los datos de una tabla improvisada se pueden copiar desde Analysis Workspace de varias formas:

* Haga clic con el botón derecho en el encabezado de tabla y seleccione **[!UICONTROL Copiar al portapapeles]**. Esto exportará la tabla completa (visible).
* Resalte celdas específicas en la tabla, haga clic con el botón secundario y seleccione **[!UICONTROL Copiar al portapapeles]** o utilice la tecla de acceso directo Ctrl + C.
* **[!UICONTROL Proyecto > Descargar CSV]**. Esto exportará todas las tablas visibles del proyecto en formato CSV.
