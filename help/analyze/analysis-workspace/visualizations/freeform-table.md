---
title: Tabla de forma libre
description: Obtenga información sobre las tablas improvisadas y el generador de tablas improvisado
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# Tabla de forma libre

En Analysis Workspace, una tabla improvisada no es simplemente una tabla de datos, sino también una visualización interactiva. Puede arrastrar y soltar una combinación de [componentes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) en las filas y columnas para crear una tabla personalizada para el análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda realizar un análisis rápido.

Puede personalizar la tabla de varias formas:

* **Filas**
   * Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Puede ajustar más filas en una sola pantalla ajustando la densidad [de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)vista del proyecto.
   * Las filas se pueden desglosar con componentes adicionales. Para desglosar muchas filas a la vez, simplemente seleccione varias filas y arrastre el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Las filas se pueden [filtrar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en Configuración [de fila](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html).

* **Columnas**
   * Los componentes se pueden apilar en columnas para crear métricas segmentadas, análisis entre fichas y mucho más.
   * La vista de cada columna se puede ajustar bajo la configuración de la [columna](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Hay varias acciones disponibles a través del menú [del botón](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)secundario. El menú proporciona diferentes acciones en función de si se hace clic en el encabezado de tabla, en las filas o en las columnas.

## Generador de tablas improvisado

Si prefiere agregar varios componentes primero a la tabla y luego procesar los datos, puede habilitar el Generador de tablas improvisado. Con el generador activado, puede arrastrar y soltar muchas dimensiones, desgloses, métricas y segmentos para crear tablas que respondan a preguntas más complejas. Los datos no se actualizarán sobre la marcha, sino que se actualizarán una vez que haga clic en **[!UICONTROL Generar]**.

El Generador de tablas es una opción que ahorra tiempo cuando tiene una pregunta compleja que hacer sobre los datos y tiene una idea de la tabla que desea crear para responder a su pregunta. Otras ventajas del generador de tablas incluyen la capacidad de:

* Organice la tabla en el formato exacto que necesite, sin tener que esperar a que se procese cada acción.
* Realice rápidamente hasta 4 niveles de desgloses.
* Defina la configuración de Fila y Desglose para cada fila de tabla y columna de dimensión.
* **[!UICONTROL Desglose por posición]**para cada nivel de la tabla de forma predeterminada (en las tablas de forma libre tradicionales, el valor predeterminado es**[!UICONTROL  Desglosar por elemento]**).
* Ordenar manualmente filas estáticas en la tabla. Por ejemplo, si desea que las filas de métricas aparezcan en un orden determinado.
* Previsualice el formato de la tabla antes de procesar datos reales.

Observe el Generador de tablas improvisadas en acción [aquí](https://youtu.be/GUMWiJAmMGI).

## Exportar datos de tabla improvisada

Los datos de una tabla improvisada se pueden copiar desde Analysis Workspace de varias formas:

* Haga clic con el botón derecho en el encabezado de tabla y seleccione **[!UICONTROL Copiar al portapapeles]**. Esto exportará la tabla completa (visible).
* Resalte celdas específicas en la tabla, haga clic con el botón derecho y seleccione **[!UICONTROL Copiar al portapapeles]**, o utilice la tecla de acceso directo Ctrl + C.
* **[!UICONTROL Proyecto > Descargar CSV]**. Esto exportará todas las tablas visibles del proyecto como un CSV.
