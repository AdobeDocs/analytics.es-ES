---
title: Personalización de informes en Adobe Analytics
description: Descubra cómo personalizar informes en Adobe Analytics
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Personalizar informes

En plataformas de terceros, como Google Analytics, hay disponibles varias opciones de personalización. Estas personalizaciones permiten al usuario crear tableros, informes personalizados, informes guardados y alertas personalizadas. Como Analysis Workspace permite a los usuarios crear informes desde un lienzo en blanco, la mayoría de las personalizaciones se integran directamente en la herramienta.

Esta página supone que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios](reports/create-report.md) de Google Analytics si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Tableros

La arquitectura de Analysis Workspace está diseñada de manera similar al concepto de utilidades de tablero. Los proyectos de Analysis Workspace son el equivalente aproximado a los tableros de Google Analytics. Las visualizaciones en Analysis Workspace son el equivalente aproximado a las utilidades de Google Analytics.

### Adición de contenido a un proyecto

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización deseada al espacio de trabajo.
2. Haga clic en el icono Componentes de la izquierda y arrastre las dimensiones y métricas deseadas a la visualización para rellenarla con datos.
3. Arrastre los bordes de la visualización para cambiar su tamaño y el título de la visualización para moverlo.

Todos los widgets de Google Analytics están disponibles en Analysis Workspace:

* La utilidad **** Métrica es aproximadamente igual a la visualización Número de resumen.
* La utilidad **Línea de tiempo** es aproximadamente igual a la visualización Línea.
* La utilidad **Geomap** es aproximadamente igual a la visualización Mapa.
* El widget **de** tabla es aproximadamente igual a la visualización de tabla improvisada.
* La utilidad **** circular es aproximadamente igual a la visualización de anillo.
* El widget **de** barra es aproximadamente igual a la visualización de barras.

Analysis Workspace incluye muchas más opciones de visualización para presentar los datos de la manera más adecuada a sus necesidades de informes. Consulte [Visualizaciones en Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) en la Guía del usuario de análisis para obtener más información.

### Uso compartido de proyectos

Una vez que haya terminado de agregar contenido a un proyecto, puede compartirlo.

* Para compartir el proyecto con sus compañeros, vaya a Compartir &gt; Compartir proyecto. Los destinatarios son otros usuarios de su organización que tienen cuentas de Adobe Analytics.
* Para compartir el proyecto mediante un vínculo, vaya a Compartir &gt; Obtener vínculo del proyecto. Tenga en cuenta que esto aún requiere iniciar sesión en Adobe Analytics dentro de su organización.

### Exportación de proyectos

Además de PDF, Analysis Workspace ofrece una exportación de CSV.

1. Haga clic en *[!UICONTROL Compartir]* &gt; *[!UICONTROL Enviar archivo ahora]*, que abre una ventana modal.
2. Especifique el tipo de archivo y los destinatarios.
3. Click [!UICONTROL Send Now].

## Informes personalizados

Al crear un informe personalizado en Google Analytics, los campos requeridos son similares al flujo de trabajo para crear una visualización en el espacio de trabajo. Las definiciones de dimensiones, métricas y filtros son similares entre plataformas. En Analysis Workspace, en lugar de seleccionar dimensiones y métricas de una lista, las dimensiones y métricas se arrastran a una tabla improvisada.

### Métricas calculadas en informes personalizados

Los informes personalizados es una de las pocas áreas de Google Analytics que permite el uso de métricas calculadas. Como Analysis Workspace funciona como un lienzo, las métricas calculadas funcionan de forma retroactiva y en cualquier contexto.

Para crear una medida calculada:

1. Haga clic en el icono **+** cerca de la lista de métricas para abrir el Creador de métricas calculadas.
2. Asigne un nombre a la métrica calculada y especifique un formato.
3. Arrastre los componentes de la métrica hasta el área de definición y utilice los menús desplegables entre cada componente para designar un operador.
4. Una vez que la métrica calculada contenga la fórmula deseada, haga clic en Guardar para volver al espacio de trabajo.
5. Arrastre la métrica calculada recién definida al espacio de trabajo.

   Obtenga más información sobre las métricas [calculadas](/help/components/c-variables/c-metrics/calculated-metric.md) en la guía del usuario Componentes.

## Alertas personalizadas

Las alertas están disponibles en ambas plataformas. En Adobe Analytics, utilice el menú de navegación de encabezado y vaya a *[!UICONTROL Componentes]* &gt; *[!UICONTROL Alertas]*. Consulte Alertas [](/help/components/c-alerts/intellligent-alerts.md) inteligentes en la Guía del usuario de componentes para obtener más información.
