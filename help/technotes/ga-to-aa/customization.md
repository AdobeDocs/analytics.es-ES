---
title: Personalización de informes en Adobe Analytics
description: Descubra cómo personalizar informes en Adobe Analytics
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '606'
ht-degree: 100%

---

# Personalizar informes

En plataformas de terceros, como Google Analytics, hay disponibles varias opciones de personalización. Estas personalizaciones permiten al usuario crear tableros, informes personalizados, informes guardados y alertas personalizadas. Ya que Analysis Workspace permite a los usuarios crear informes desde un lienzo en blanco, la mayoría de las personalizaciones están integradas directamente en la herramienta.

En esta página se da por hecho que el usuario tiene conocimientos básicos sobre el uso de [!UICONTROL Analysis Workspace]. Consulte [Creación de un informe básico en Analysis Workspace para usuarios de Google Analytics](reports/create-report.md) si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Tableros

La arquitectura de [!UICONTROL Analysis Workspace] está diseñada de manera similar al concepto de widgets de tablero. Los proyectos de [!UICONTROL Analysis Workspace] son el equivalente de los tableros de Google Analytics. Las visualizaciones en [!UICONTROL Analysis Workspace] son el equivalente aproximado de los widgets de Google Analytics.

### Adición de contenido a un proyecto

1. Haga clic en el icono [!UICONTROL Visualizaciones] de la izquierda y arrastre la visualización deseada al espacio de trabajo.
2. Haga clic en el icono [!UICONTROL Componentes] de la izquierda y arrastre las dimensiones y métricas deseadas a la visualización para rellenarla con datos.
3. Arrastre los bordes de la visualización para cambiar su tamaño y el título de la visualización para moverlo.

Todos los widgets de Google Analytics están disponibles en [!UICONTROL Analysis Workspace]:

* El **widget Métrica** es aproximadamente igual a la visualización [!UICONTROL Número de resumen].
* El **widget Cronología** es aproximadamente igual a la visualización [!UICONTROL Línea].
* El **widget Geomap** es aproximadamente igual a la visualización [!UICONTROL Mapa].
* El **widget de tabla** es aproximadamente igual a la visualización de [!UICONTROL tabla de forma libre].
* El **widget circular** es aproximadamente igual a la visualización de [!UICONTROL anillos].
* El **widget de barra** es aproximadamente igual a la visualización de [!UICONTROL barras].

[!UICONTROL Analysis Workspace] incluye muchas más opciones de visualización para presentar los datos de la manera más adecuada según sus necesidades. Consulte [Visualizaciones en Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) en la Guía del usuario de análisis para obtener más información.

### Uso compartido de proyectos

Una vez que haya terminado de agregar contenido a un proyecto, puede compartirlo.

* Para compartir el proyecto con sus compañeros, vaya a **[!UICONTROL Compartir > Compartir proyecto]**. Los destinatarios son otros usuarios de su organización que tienen cuentas de Adobe Analytics.
* Para compartir el proyecto mediante un vínculo, vaya a **[!UICONTROL Compartir > Obtener vínculo del proyecto]**. Tenga en cuenta que es necesario que su organización tenga credenciales de Adobe Analytics.

### Exportación de proyectos

Además de PDF, [!UICONTROL Analysis Workspace] ofrece exportación a CSV.

1. Haga clic en *[!UICONTROL Compartir]* > *[!UICONTROL Enviar archivo ahora]*, que abre una ventana modal.
2. Especifique el tipo de archivo y los destinatarios.
3. Haga clic en [!UICONTROL Enviar ahora].

## Informes personalizados

Al crear un informe personalizado en Google Analytics, los campos necesarios son similares al flujo de trabajo para crear una visualización en el espacio de trabajo. Las definiciones de dimensiones, métricas y filtros son similares entre plataformas. En Analysis Workspace, en lugar de seleccionar dimensiones y métricas de una lista, las dimensiones y métricas se arrastran a una tabla de forma libre.

### Métricas calculadas en informes personalizados

El área de informes personalizados es una de las pocas de Google Analytics que permite el uso de métricas calculadas. Ya que Analysis Workspace funciona como un lienzo, las métricas calculadas se utilizan de forma retroactiva y en cualquier contexto.

Para crear una medida calculada:

1. Haga clic en el icono **+** cerca de la lista de métricas para abrir el [!UICONTROL Creador de métricas calculadas]. 
2. Asigne un nombre a la métrica calculada y especifique un formato.
3. Arrastre los componentes de la métrica hasta el área de definición y utilice los menús desplegables entre cada componente para designar un operador.
4. Una vez que la métrica calculada contenga la fórmula deseada, haga clic en Guardar para volver al espacio de trabajo.
5. Arrastre la métrica calculada recién definida al espacio de trabajo.

   Obtenga más información sobre las [métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) en la Guía del usuario de componentes.

## Alertas personalizadas

Las alertas están disponibles en ambas plataformas. En Adobe Analytics, utilice el menú de navegación de encabezado y vaya a *[!UICONTROL Componentes]* > *[!UICONTROL Alertas]*. Consulte [Alertas inteligentes](/help/components/c-alerts/intellligent-alerts.md) en la Guía del usuario de componentes para obtener más información.
