---
title: Informes de comportamiento en Adobe Analytics
description: Cómo crear informes de comportamiento en Adobe Analytics
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Informes de comportamiento

Los informes de comportamiento muestran información sobre cómo los usuarios interactúan con el sitio.

En esta página se asume que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Flujo de comportamiento

El informe de flujo de comportamiento se puede volver a crear con la visualización de Flujo.

1. Haga clic en el icono de visualizaciones a la izquierda y arrastre una visualización de Flujo al espacio de trabajo encima de la tabla improvisada.
2. Locate the **Page** dimension, then click the Arrow icon to reveal page values. Los valores de dimensión se colorean en color amarillo.
3. Busque el valor de página que desee para comenzar y arrástrelo al espacio rotulado'Dimensión o elemento'en el centro.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos con páginas anteriores o anteriores. Utilice el menú de clic derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

![Informe Flujo](../assets/flow.png)

## Contenido del sitio - Todas las páginas

El informe de páginas muestra el rendimiento de las páginas individuales del sitio.

1. In the Components menu, locate the **Pages** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Como alternativa, Adobe proporciona varios espacios de trabajo creados previamente, llamados plantillas. La plantilla Consumo de contenido (Web) proporciona un valor similar al de todas las páginas.

1. Click *[!UICONTROL Project]&gt;[!UICONTROL New]*, which opens a modal window with project options.
2. Haga clic en la plantilla Consumo de contenido (Web) y, a continuación, haga clic en Crear.

## Contenido del sitio - Exploración de contenido

El informe de exploración de contenido permite mirar el tráfico de la página por estructura de URL. Se requiere de implementación adicional para usar en Analysis Workspace. Adobe recomienda trabajar con un asesor de implementación para garantizar que estos datos se recopilen con precisión.

## Contenido del sitio - Páginas de aterrizaje

El informe de páginas de aterrizaje muestra las páginas de aterrizaje principales del sitio. Landing pages are available in Analysis Workspace as the **Entry Page** dimension.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## Contenido del sitio - Páginas de salida

El informe de páginas de salida muestra las páginas más visitadas que fueron la última página de la visita individual de una persona. Está disponible en Analysis Workspace con el mismo nombre.

1. In the Components menu, locate the **Exit Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## Informes de velocidad del sitio

Los informes de velocidad del sitio muestran la rapidez con la que se cargan las páginas, revelando oportunidades para aumentar los tiempos de carga de la página.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un asesor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. The [Performance Timing plugin](../../../implement/js-implementation/plugins/performancetiming.md) is typically assigned to an eVar to obtain performance data in Adobe Analytics.

## Informes de búsqueda del sitio

Los informes de búsqueda del sitio proporcionan información sobre cómo utilizan los visitantes las capacidades de búsqueda interna del sitio.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un asesor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. Generalmente, un término de búsqueda interna se extrae de un parámetro de cadena de consulta y se coloca en una evar para los informes.

## Informes de eventos

Los eventos tienen algunas diferencias estructurales principales entre Google y Adobe Analytics. Ambos requieren cambios de implementación adicionales para funcionar correctamente en su respectiva plataforma.

* En Google Analytics, los eventos se definen en su implementación como texto. Los eventos tienen categorías, acciones y etiquetas.
* En Adobe Analytics, los eventos se configuran primero en Admin Console, donde se asigna un identificador. Este identificador se utiliza en el código de implementación. Por ejemplo:
   1. Puede establecer event 1 en Admin Console como'Registros '.
   2. En la implementación, incluiría event 1 en la variable events en la página de confirmación de registro. Cada vez que se muestra la página de confirmación de registro, el evento 1 aumenta.
   3. En Analysis Workspace, «Registros» aparece como una métrica para utilizarla en cualquier informe.

Puesto que esta función requiere cambios de implementación, Adobe recomienda trabajar con un asesor de implementación para garantizar que los datos estén correctamente configurados para Analysis Workspace.

## Informes de editor

De manera similar a cómo Google requiere una conexión con Google Ad Manager, Adobe ofrece un producto dedicado para proporcionar una perspectiva llamada Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
