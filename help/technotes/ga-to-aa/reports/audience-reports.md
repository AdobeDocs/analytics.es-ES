---
title: Informes de audiencia en Adobe Analytics
description: Aprenda a crear informes basados en audiencias mediante Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Informes de audiencia

Los informes de audiencia muestran información sobre los tipos de personas que visitan el sitio.

En esta página se asume que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Usuarios activos

Los usuarios activos muestran el número acumulado de usuarios al sitio en los 1, 7, 14 o 28 días anteriores. Aunque Adobe no tiene el cálculo exacto utilizado en Google Analytics, puede utilizar la métrica Visitantes únicos para ver un recuento desdoblado de usuarios en el sitio según el intervalo de fechas seleccionado.

Para obtener un gráfico de líneas de visitantes únicos:

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización de línea al espacio de trabajo por encima de la tabla improvisada vacía.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled 'Drop a Metric here'.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) sobre el encabezado de dimensión de fecha existente.

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## Valor de duración

El valor de duración es una característica que requiere una implementación especializada adicional en ambas plataformas. Adobe recomienda trabajar con un asesor de implementación para obtener estos datos.

## Análisis de cohorte

Análisis de cohorte muestra la frecuencia con la que los mismos usuarios regresan al sitio.

Para crear una tabla de cohorte:

1. Haga clic en el icono Visualización de la izquierda y arrastre la visualización Tabla de cohorte al espacio de trabajo.
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. Haga clic en Crear.

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## Audiencias

El informe Audiencias de Google Analytics requiere la configuración de audiencias. Las audiencias también requieren configuración en Adobe a través de Adobe Audience Manager. Consulte la guía del usuario de Adobe Audience Manager para obtener más información.

## Usuario Explorer

El informe Explorador de usuarios permite a un analista ver visitas individuales a través de identificadores anónimos. Adobe no recorta los identificadores back-end fuera de las fuentes de datos, que son exportaciones de datos sin procesar en el nivel de visita.

* Si se desean estos datos en Analysis Workspace, es posible trabajar con un consultor de implementación para pasar el valor único de cookie de identificación única a una evar. Tenga en cuenta que esto solo funciona con implementaciones menores que constan de menos de 1 millón de visitantes únicos al mes.
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## Informes demográficos e intereses

Los datos demográficos e intereses proporcionan información sobre la edad, el sexo y los intereses de los usuarios del sitio. Google recopila esos datos a través de su capacidad de seguimiento entre sitios.

Adobe no recopila automáticamente los datos demográficos e intereses. Sin embargo, si su organización obtiene estos datos, puede utilizar Atributos del cliente, una función de la plataforma Adobe Experience Cloud. Permite controlar completamente la organización de datos por atributos y no está limitada únicamente a los intereses demográficos o a los intereses.

Consulte la Ayuda de Atributos del cliente para obtener más información.

## Geo - Language

El informe de idioma geográfico muestra el tráfico del sitio según la configuración del idioma en el explorador del visitante.

Para crear un informe de idioma:

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## Ubicación geográfica: ubicación

El informe de ubicación geográfica proporciona una vista de mapa mundial, desglosar los datos por país.

Para crear un informe de ubicación geográfica:

1. Haga clic en el icono Visualizaciones a la izquierda y arrastre la visualización Mapa al espacio de trabajo por encima de la tabla improvisada vacía.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled 'Add Metric'.
3. Haga clic en Crear.

Si la tabla también se desea además del mapa:

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## Comportamiento: Nuevo frente a Retorno

El nuevo informe vs. devuelve una vista simplificada de las primeras sesiones (nuevas visitas) vs. sesiones posteriores (visitas de retorno).

Para crear un informe de visitas nuevo frente a visitas:

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled 'Drop a Dimension here'. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. Esto agrega el segmento como una dimensión debajo de Visitas por primera vez, lo que permite una comparación fácil.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Si también desea un gráfico de líneas:

1. Haga clic en el icono de visualizaciones a la izquierda y arrastre una visualización de línea al espacio de trabajo encima de la tabla improvisada.
2. Utilice ctrl + clic (Windows) o cmd + clic (Mac) en cada fila de la tabla improvisada para resaltarlos. Esto permite que ambas tendencias aparezcan en la visualización de líneas.
3. Haga clic en el pequeño punto de color redonda en la esquina superior izquierda de la visualización de líneas y, a continuación, haga clic en la casilla'Bloquear selección '.

## Comportamiento: Frecuencia y actualización

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## Comportamiento: participación

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## Tecnología: Explorador y sistema operativo

Hay varias dimensiones principales disponibles en el informe Explorador y sistema operativo.

* The **Browser** primary dimension is also available in Analysis Workspace as a dimension.
* The **Operating System** primary dimension is also available in Analysis Workspace as a dimension.
* The **Screen Resolution** primary dimension is available in Analysis Workspace as the **Monitor Resolution** dimension.
* The **Screen Colors** primary dimension is available in Analysis Workspace as the **Color Depth** dimension.
* The **Flash Version** primary dimension is not available in Adobe Analytics, however this data can be collected by an eVar if wanted.

1. En el menú de componentes, busque la dimensión que desee arriba y arrástrela al área de tabla improvisada grande rotulada «Arrastrar una dimensión aquí».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Consulte las páginas siguientes en la guía del usuario de Componentes para obtener más información sobre su respectiva dimensión:

* [Navegador](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [Sistema operativo](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [Resolución del monitor](../../../components/c-variables/dimensionslist/reports-technology.md)
* [Profundidad de color](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## Tecnología - Red

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## Móvil - Información general

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. Tenga en cuenta que el valor'Otro'equivale al tráfico de escritorio.

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## Móvil - Dispositivos

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## Personalizado

Los informes personalizados se definen por implementación. Trabaje con el administrador de Analytics y/o asesor de implementación de su organización para interpretar estos informes. Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## Referencia

La comparación de informes permite ver cómo se comparan los datos de los datos con los promedios del sector. Adobe no comparte datos de referencia entre sus clientes en este momento.

## Flujo de usuarios

El informe de flujo está disponible en ambas plataformas. Para crear un informe de flujo:

1. Haga clic en el icono de visualizaciones a la izquierda y arrastre una visualización de Flujo al espacio de trabajo encima de la tabla improvisada.
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Los valores de dimensión se colorean en color amarillo.
3. Busque el valor de página que desee para comenzar y arrástrelo al espacio rotulado'Dimensión o elemento'en el centro.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos con páginas anteriores o anteriores. Utilice el menú de clic derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.
