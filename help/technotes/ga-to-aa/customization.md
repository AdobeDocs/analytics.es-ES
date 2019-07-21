---
title: Personalización de informes en Adobe Analytics
description: Cómo personalizar informes en Adobe Analytics
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Personalizar informes

En plataformas de terceros, como Google Analytics, hay varias opciones de personalización disponibles. Estas personalizaciones permiten al usuario crear tableros, informes personalizados, informes guardados y alertas personalizadas. Puesto que Analysis Workspace permite a los usuarios crear informes desde un lienzo en blanco, la mayoría de las personalizaciones se genera directamente en la herramienta.

En esta página se asume que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Tableros

La arquitectura de Analysis Workspace se crea de forma similar al concepto de widgets de tableros. Los proyectos de Analysis Workspace son el equivalente aproximado a los tableros en Google Analytics. Las visualizaciones de Analysis Workspace son el equivalente aproximado a las utilidades de Google Analytics.

### Adición de contenido a un proyecto

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización que desee al espacio de trabajo.
2. Haga clic en el icono Componentes a la izquierda y arrastre las dimensiones y métricas deseadas a la visualización para completarla con datos.
3. Arrastre los bordes de la visualización para cambiar su tamaño y arrastre el título de la visualización para moverlo.

Todas las utilidades de Google Analytics están disponibles en Analysis Workspace:

* The **Metric widget** is approximately equal to the Summary Number visualization.
* The **Timeline widget** is approximately equal to the Line visualization.
* The **Geomap widget** is approximately equal to the Map visualization.
* The **Table widget** is approximately equal to the Freeform Table visualization.
* The **Pie widget** is approximately equal to the Donut visualization.
* The **Bar widget** is approximately equal to the Bar visualization.

Analysis Workspace incluye muchas más opciones de visualización para presentar los datos de una manera más adecuada para sus necesidades de informes. See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### Uso compartido de proyectos

Una vez que haya terminado de agregar contenido a un proyecto, puede compartirlo.

* Para compartir el proyecto con sus compañeros, vaya a Compartir &gt; Compartir proyecto. Los destinatarios son otros usuarios de su organización que tienen cuentas de Adobe Analytics.
* Para compartir el proyecto a través de un vínculo, vaya a Compartir &gt; Obtener vínculo del proyecto. Tenga en cuenta que esto sigue necesitando iniciar sesión en Adobe Analytics dentro de su organización.

### Exportación de proyectos

Además de PDF, Analysis Workspace ofrece una exportación CSV.

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. Especifique el tipo de archivo y los destinatarios.
3. Click [!UICONTROL Send Now].

## Informes personalizados

Al crear un informe personalizado en Google Analytics, los campos requeridos son similares al flujo de trabajo al crear una visualización en el espacio de trabajo. Las dimensiones, las métricas y las definiciones de filtro son similares entre plataformas. En Analysis Workspace, en lugar de seleccionar dimensiones y métricas de una lista, las dimensiones y métricas se arrastran a una tabla improvisada.

### Métricas calculadas en informes personalizados

Los informes personalizados son una de las pocas áreas de Google Analytics que permite el uso de métricas calculadas. Como Analysis Workspace funciona como un lienzo, las métricas calculadas funcionan de forma retroactiva y en cualquier contexto.

Para crear una medida calculada:

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. Asigne un nombre a la métrica calculada y especifique un formato.
3. Arrastre los componentes de métricas hasta el área de definición y utilice los desplegables entre cada componente para designar un operador.
4. Una vez que la métrica calculada contenga la fórmula deseada, haga clic en Guardar para volver al espacio de trabajo.
5. Arrastre la métrica calculada recientemente definida al espacio de trabajo.

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## Alertas personalizadas

Las alertas están disponibles en ambas plataformas. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
