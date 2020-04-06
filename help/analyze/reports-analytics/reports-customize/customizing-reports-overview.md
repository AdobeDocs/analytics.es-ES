---
description: Después de ejecutar un informe, puede personalizar el informe para realizar una vista y analizar los datos según sus necesidades. Puede filtrar los datos del informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.
title: Resumen de los informes personalizados
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen de los informes personalizados

Después de ejecutar un informe, puede personalizar el informe para realizar una vista y analizar los datos según sus necesidades. Puede filtrar los datos del informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.

## Crear un informe personalizado {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Instrucciones sobre cómo guardar la configuración actual de un informe como un nuevo informe personalizado para que lo vean todos los usuarios.

<!-- 

t_reports_custom.xml

 -->

Solo los administradores pueden crear un informe personalizado. Al crear un informe personalizado, éste se agrega al menú de sistema de informes principal junto al informe en el que se basa.

**Para crear un informe personalizado**

1. Ejecute un informe y configúrelo según sea necesario.
1. Haga clic **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   Asegúrese de que no haya repetido el nombre de otro informe ya existente.

>[!MORELIKETHIS]
>
>* [Personalización de menús](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/customize-menus.translate.html)


## Seleccionar una fecha o un intervalo de fecha {#task_9BEF7D4D839A4748B76E8500D1406C34}

Instrucciones sobre cómo elegir los períodos de tiempo para los datos del informe.

<!-- 

t_reports_select_date.xml

 -->

Puede seleccionar días, semanas, meses o años específicos. También puede ejecutar informes de comparación.

Cuando abre un panel con informes breves que tienen diferentes intervalos de fechas, puede elegir un nuevo intervalo de fechas en el calendario. Los cambios se aplican a todos los informes breves del panel.

**Para seleccionar un intervalo de fechas**

1. Ejecutar un informe.
1. Haga clic en el icono de calendario de la parte superior derecha.
1. Seleccione una fecha.

   Puede:

   * Días de Vista, meses o períodos de año (hasta tres).
   * Arrastre el cursor por las fechas para seleccionar un intervalo.
   * Escriba las fechas manualmente.
   * Haga clic en el nombre de un mes para seleccionar un mes.
   * Haga clic en **[!UICONTROL Select Preset]** para seleccionar una fecha preestablecida.
   * Comparar fechas.

1. Haga clic en **[!UICONTROL Run Report]**.

## Comparar fechas {#task_95155C3700774B709F5FB81AE96B0824}

Instrucciones sobre cómo utilizar el calendario para ejecutar comparaciones de fechas entre informes de clasificación.

<!-- 

t_reports_comparing_dates.xml

 -->

No puede comparar fechas entre informes de tendencias.

>[!NOTE] Si desea llevar a cabo una comparación por fechas en métricas clave en un panel, puede extraer los datos en el [Report Builder](https://marketing.adobe.com/resources/help/es_ES/arb/) mediante dos solicitudes independientes. A continuación, puede usar fórmulas personalizadas en Excel para analizar la diferencia entre ambos.

Para comparar fechas entre informes de clasificación en Informes y análisis:

1. Ejecutar un informe.
1. Haga clic en el calendario en la parte superior.
1. Haga clic en **[!UICONTROL Compare Dates]**.
1. Seleccione las fechas que desee utilizar.
1. Haga clic en **[!UICONTROL Run Report]**.

## Mostrar un porcentaje como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Instrucciones sobre cómo especificar si se muestra el porcentaje en una tabla del informe como un gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

Esta visualización también está disponible en los informes breves de panel.

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. Haga clic en **[!UICONTROL Percent Shown As: Graph]**.

## Normalizar datos de informes {#task_8005B55E59BD479DA67BC618FF8BC94A}

Instrucciones sobre cómo normalizar los datos de los informes.

<!-- 

t_reports_normalize.xml

 -->

Después de ejecutar un informe con fechas comparadas, o para comparaciones A/B, puede normalizar los datos para mostrar el porcentaje de cambio entre los informes. El conjunto de datos secundario se ajusta para compensar las diferencias en el número de días seleccionados o en los distintos volúmenes de tráfico.

**Para normalizar los datos del informe**

1. Ejecute un informe que sea compatible con las comparaciones de fechas.
1. Haga clic en **[!UICONTROL Compare Dates]**, luego especifique la comparación de fechas.
1. Haga clic en **[!UICONTROL Run Report]**.
1. Haga clic en **[!UICONTROL Normalize Data: Yes]**.

## Seleccionar una página para un informe {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Instrucciones sobre cómo seleccionar una página concreta de entre las páginas del sitio web, para un informe.

<!-- 

t_reports_select_page.xml

 -->

1. Genere un informe, como un [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1. Busque la página.
1. Haga clic en **[!UICONTROL OK.]**

## Comparar grupos de informes {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Instrucciones sobre cómo mostrar informes de dos grupos de informes en el mismo informe.

<!-- 

t_reports_compare_suites.xml

 -->

Además de la visualización gráfica, la tabla del informe proporciona una comparación de porcentajes. Los siguientes informes se pueden ejecutar con comparaciones:

* Contenido del sitio
* Mobile
* Fuentes de tráfico
* Campañas
* Productos
* Retención de visitantes
* Perfil del visitante
* Conversión personalizada
* Tráfico personalizado
* Target
* Encuesta

**Para comparar grupos de informes**

1. Genere un informe que le permita comparar informes.
1. Click the **[!UICONTROL Compare to Site]** link.
1. Busque el grupo de informes.
1. Haga clic en **[!UICONTROL OK.]**

## Especificar la granularidad de los informes {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Instrucciones sobre cómo realizar la vista de los totales de los informes por hora, por día, por semana, por mes, por trimestre o por año.

<!-- 

t_reports_granularity.xml

 -->

El período de tiempo del informe determina qué opciones de granularidad están disponibles. Por ejemplo, solo puede seleccionar **[!UICONTROL Hourly]** si tiene un intervalo de tiempo de uno o dos días seleccionado. Solo puede seleccionar **[!UICONTROL Yearly]** la granularidad si ha seleccionado más de un año.

**Para especificar la granularidad del informe**

1. Genere un informe de tendencias, como **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## Ejecutar un informe de día de la semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Instrucciones sobre cómo ejecutar informes en un día específico de la semana, como por ejemplo cada lunes en un intervalo de fechas determinado.

<!-- 

t_reports_day_of_week.xml

 -->

Esta función solo se aplica a los informes de tendencias filtrados con un intervalo de fechas de semana o día.

1. Ejecute un informe de tendencias en un intervalo de fechas específico.
1. Haga clic en el **[!UICONTROL Day of Week]** vínculo y, a continuación, haga clic en un día.

## Botón “Probar en el espacio de trabajo” {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Al hacer clic en el **[!UICONTROL Try In Workspace]** botón en la parte superior de un informe, se cargará el mismo informe en Análisis Workspace.

<!-- 

try_in_workspace.xml

 -->

La mayoría de los informes de Informes y análisis ahora incluyen el botón &quot;Probar en el espacio de trabajo&quot; para permitirle reproducir la vista actual en el espacio de trabajo de Análisis y personalizarla más.

Actualmente, el botón solo está disponible si el nombre de usuario tiene derechos completos en Espacio de trabajo de Análisis.

Para obtener más información sobre todas las formas de personalizar el informe, consulte la guía [Análisis de espacio de trabajo](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/) .
