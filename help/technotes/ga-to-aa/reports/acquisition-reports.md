---
title: Informes de adquisición en Adobe Analytics
description: Aprenda a crear informes basados en adquisición mediante Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Informes de adquisición

Los informes de adquisición muestran cómo se obtienen los visitantes del sitio.

In Adobe Analytics, these reports are known as **Marketing Channels**. Requieren una configuración inicial básica, pero permiten una visualización mucho más personalizada de los canales.

> [!IMPORTANT]
>
> Configure las reglas de procesamiento del canal de mercadotecnia para utilizar estos informes. See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

En esta página se asume que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Todo el tráfico: canales

Muestra una vista agregada de todos los canales que utilizan los visitantes para llegar al sitio.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Todo tráfico - Presentaciones

Muestra un rectángulo del tráfico de canal. Este informe es similar a Todo tráfico: canales, pero se muestra de manera diferente.

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización de Treemap al espacio de trabajo por encima de la tabla improvisada vacía.
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled 'Drop a dimension here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. Tenga en cuenta que las métricas adicionales crean otros rectángulos. Si solo se desea un rectángulo:
   1. Haga clic en la celda superior de la métrica que desee para representar el rectángulo.
   2. Mayús + clic en la última celda de la misma columna de métrica para resaltar la columna azul. Si se realiza correctamente, hay un gráfico de rectángulos en la visualización.
   3. Haga clic en el punto coloreado en la esquina superior derecha de la visualización de rectángulos y, a continuación, haga clic en la casilla'Bloquear selección '.

Los gráficos de rectángulos se pueden aplicar a cualquier dimensión, no solo a los canales de marketing.

## Tráfico completo: fuente/medio

Los informes de origen y media muestran los dominios que condujeron el tráfico al sitio.

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Medium** primary dimension is available in Analysis Workspace as the  **Referrer Type** dimension.
* The **Keyword** primary dimension is available in Analysis Workspace as the **Search Keyword** dimension.

1. En el menú de componentes, busque la dimensión que desee arriba y arrástrela al área de tabla improvisada grande rotulada «Arrastrar una dimensión aquí».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Consulte las páginas siguientes en la guía del usuario de Componentes para obtener más información sobre su respectiva dimensión:

* [Dominio de referencia](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [Tipo de referente](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [Palabra clave de búsqueda](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## Tráfico completo: referencias

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Landing Page** primary dimension is available in Analysis Workspace as the **Entry Page** dimension.

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Informes de Google Ads y informes de la Consola de búsqueda

Adobe utiliza una función de Analysis Workspace denominada Advertising Analytics para aportar datos de publicidad y búsqueda de varias plataformas, incluido Google.

La función de análisis de publicidad requiere la configuración para devolver datos. See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Informes sociales 

Los informes de Social proporcionan información similar como el informe de comportamiento respectivo, excepto en el contexto de las redes sociales. Estos datos están disponibles en Analysis Workspace combinando una dimensión con un segmento.

A veces, los visitantes llegan al sitio a través de varios canales en la misma sesión. Por ejemplo, un visitante hace clic en una página de medios sociales, luego unos minutos después visita un motor de búsqueda para llegar al sitio. En estos casos, los dominios no sociales pueden aparecer en este informe. Si desea excluir dominios no sociales, ordene el informe por visitas o cree una copia del segmento para que se base en visitas individuales en lugar de visitas. See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social: referencias de red

El informe Referencias de red muestra qué dominios de redes sociales condujeron el tráfico al sitio. This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Páginas de aterrizaje

El informe Páginas de aterrizaje muestra a qué páginas llegaron los visitantes después de hacer clic en un vínculo a través de una red social. This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Conversiones

El informe Conversiones muestra los datos de comercio electrónico en contexto de las redes sociales. Se requiere de implementación adicional para utilizar estos informes en ambas plataformas; Adobe recomienda trabajar con un asesor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace.

### Social - Complementos

El informe Complementos muestra cómo los visitantes interactúan con los complementos de medios sociales incrustados en el sitio. Se requiere de implementación adicional para usar en Analysis Workspace. Adobe recomienda trabajar con un asesor de implementación para garantizar que estos datos se recopilen con precisión.

### Social - Flujo de usuarios

El informe de flujo de usuarios muestra los datos de ruta en el contexto de visitantes que llegan a través de una red social.

1. Haga clic en el icono de visualizaciones a la izquierda y arrastre una visualización de Flujo al espacio de trabajo encima de la tabla improvisada.
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled 'Drop a Segment here'.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Los valores de dimensión se colorean en color amarillo.
4. Busque el valor de página que desee para comenzar y arrástrelo al espacio rotulado'Dimensión o elemento'en el centro.
5. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos con páginas anteriores o anteriores. Utilice el menú de clic derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

## Campañas - Todo

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. Tenga en cuenta que el uso de la dimensión Código de seguimiento requiere una implementación adicional para recopilar datos.

Es posible recopilar parámetros UTM en Adobe Analytics mediante variables personalizadas (evars). Adobe recomienda trabajar con un asesor de implementación para garantizar que los valores del código de seguimiento se recopilen correctamente en Adobe Analytics.

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campañas: palabras clave pagas

El informe de palabras clave pagas muestra cómo funciona cada palabra clave después de que un visitante hace clic en un vínculo de búsqueda paga desde un motor de búsqueda. The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campañas - Palabras clave orgánicas

El informe Palabras clave orgánicas muestra cómo funciona cada palabra clave después de que un visitante hace clic en un vínculo de búsqueda orgánica desde un motor de búsqueda. The **Search Keywords - Natural** dimension is available in Analysis Workspace. Tenga en cuenta que si la detección de búsqueda paga no está configurada, esta dimensión recopila palabras clave naturales y pagas.

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Análisis de costos

Este informe muestra los datos de rendimiento de visitas, costos y ingresos de los canales de mercadotecnia paga. Adobe ofrece un producto dedicado para proporcionar una perspectiva denominada Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
