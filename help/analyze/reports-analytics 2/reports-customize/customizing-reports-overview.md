---
description: Después de ejecutar un informe, puede personalizarlo para ver y analizar los datos según sus necesidades. Puede filtrar los datos de informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.
title: Resumen de los informes personalizados
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 79%

---

# Personalizar informes

Después de ejecutar un informe, puede personalizarlo para ver y analizar los datos según sus necesidades. Puede filtrar los datos de informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.

## Seleccionar una fecha o un intervalo de fecha {#task_9BEF7D4D839A4748B76E8500D1406C34}

Puede elegir los períodos de tiempo para los datos del informe.

<!-- 

t_reports_select_date.xml

 -->

Puede seleccionar días, semanas, meses o años específicos. También puede ejecutar informes de comparación.

Al abrir un tablero con informes breves que tengan distintos intervalos de fecha, puede elegir un nuevo intervalo de fecha en el calendario. Los cambios se aplicarán a todos los informes breves del tablero.

Para seleccionar un intervalo de fecha:

1. Ejecutar un informe.
1. Haga clic en el icono de calendario de la parte superior derecha.
1. Seleccione una fecha.

   Puede:

   * Ver los periodos de días, meses o años (hasta tres).
   * Arrastrar el cursor por las fechas para seleccionar un intervalo.
   * Escribir fechas de forma manual.
   * Hacer clic en el nombre de un mes para seleccionar un mes.
   * Hacer clic en **[!UICONTROL Seleccionar valores preestablecidos]** para seleccionar una fecha preestablecida.
   * Comparar fechas.

1. Haga clic en **[!UICONTROL Ejecutar informe]**.

## Comparar fechas {#task_95155C3700774B709F5FB81AE96B0824}

Puede utilizar el calendario para ejecutar comparaciones de fechas entre informes de clasificación.

<!-- 

t_reports_comparing_dates.xml

 -->

No puede comparar las fechas entre los informes de tendencia.

>[!NOTE]
>
>Si desea llevar a cabo una comparación por fechas en métricas clave en un panel, puede extraer los datos en el [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es) mediante dos solicitudes independientes. A continuación, puede usar fórmulas personalizadas en Excel para analizar la diferencia entre ambos.

<!-- delete this procedure, but what about this entire "Compare dates" section?

To compare dates between ranked reports in Reports & analytics: 

1. Run a report.
1. Click the calendar at the top right.
1. Click **[!UICONTROL Compare Dates]**.
1. Select the dates you want to use.
1. Click **[!UICONTROL Run Report]**.

-->

## Mostrar un porcentaje como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Puede especificar si desea mostrar el porcentaje en una tabla de un informe como un gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

Esta visualización también está disponible en informes breves de tableros.

Para mostrar el porcentaje como un gráfico en una tabla de informe:

1. Ejecute un informe compatible con porcentajes como, por ejemplo, un [!UICONTROL Informe de páginas].
1. Haga clic en **[!UICONTROL El porcentaje se muestra como: Gráfico]**.

## Normalizar datos de informes {#task_8005B55E59BD479DA67BC618FF8BC94A}

<!-- 

t_reports_normalize.xml

 -->

Después de ejecutar un informe con fechas comparadas, o comparaciones A/B, puede normalizar los datos para mostrar el porcentaje de cambio entre los informes. El conjunto de datos secundarios se ajusta para compensar las diferencias en el número de días seleccionados o en los distintos volúmenes de tráfico.

Para normalizar los datos del informe:

1. Ejecute un informe que sea compatible con las comparaciones de fechas.
1. Haga clic en **[!UICONTROL Comparar fechas]** y, luego, especifique la comparación de fechas.
1. Haga clic en **[!UICONTROL Ejecutar informe]**.
1. Haga clic en **[!UICONTROL Normalizar datos: Sí]**.

## Seleccionar una página para un informe {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Para seleccionar una página específica de las páginas del sitio web para un informe:

<!-- 

t_reports_select_page.xml

 -->

1. Genere un informe, como por ejemplo un [!UICONTROL informe Vistas de página] (**[!UICONTROL Informes]** > **[!UICONTROL Métrica del sitio]** > **[!UICONTROL Vistas de páginas]**).
1. Haga clic en el vínculo **[!UICONTROL Página seleccionada]**.
1. En [!UICONTROL Elegir página], seleccione las páginas que desee mostrar.
1. Busque la página.
1. Haga clic en **[!UICONTROL Aceptar]**.

## Comparar grupos de informes {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Puede mostrar informes de dos grupos de informes en el mismo informe.

<!-- 

t_reports_compare_suites.xml

 -->

Además de la representación gráfica, la tabla del informe proporciona una comparación porcentual. Los siguientes informes se pueden ejecutar con comparaciones:

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

Para comparar grupos de informes:

1. Genere un informe que le permita comparar informes.
1. Haga clic en el vínculo **[!UICONTROL Comparar con otro sitio]**.
1. Busque el grupo de informes.
1. Haga clic en **[!UICONTROL Aceptar]**.

## Especificar la granularidad de los informes {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Puede ver los totales del informe por horas, días, semanas, meses, trimestrales o años.

<!-- 

t_reports_granularity.xml

 -->

El periodo de tiempo del informe determina qué opciones de granularidad se encuentran disponibles. Por ejemplo, puede elegir solo **[!UICONTROL Por hora]** si tiene un intervalo de tiempo de uno o dos días seleccionado. Solo puede seleccionar la granularidad **[!UICONTROL Por año]** si tiene más de un año seleccionado.

Para especificar la granularidad del informe:

1. Genere un informe de tendencia como, por ejemplo, **[!UICONTROL Contenido del sitio]** > **[!UICONTROL Páginas]**.
1. Haga clic en el vínculo **[!UICONTROL Ver por]** y, a continuación, haga clic en una granularidad.

## Ejecutar un informe de día de la semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Los informes se pueden ejecutar en un día de la semana específico, por ejemplo, todos los lunes de un intervalo de fechas determinado.

<!-- 

t_reports_day_of_week.xml

 -->

Esta función se aplica solamente a los informes de tendencia filtrados con un intervalo de fechas de semana o día.

Para ejecutar un informe de día de la semana:

1. Ejecute un informe de tendencias en un intervalo de fechas específico.
1. Haga clic en el vínculo **[!UICONTROL Día de la semana]** y, a continuación, haga clic en un día.
