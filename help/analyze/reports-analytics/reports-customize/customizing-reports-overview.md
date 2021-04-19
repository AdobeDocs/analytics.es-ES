---
description: Después de ejecutar un informe, puede personalizarlo para ver y analizar los datos según sus necesidades. Puede filtrar los datos de informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.
title: Resumen de los informes personalizados
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Conceptos básicos de Reports & Analytics y conceptos básicos de Analytics
role: Business Practitioner, Administrator
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 99%

---

# Resumen de los informes personalizados

Después de ejecutar un informe, puede personalizarlo para ver y analizar los datos según sus necesidades. Puede filtrar los datos de informe, cambiar la forma en que se presentan los datos gráficamente, cambiar la granularidad de la fecha, etc.

## Crear un informe personalizado {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Instrucciones sobre cómo guardar la configuración actual de un informe como un nuevo informe personalizado, para que lo vean todos los usuarios.

<!-- 

t_reports_custom.xml

 -->

Solo los administradores pueden crear un informe personalizado. Cuando crea un informe personalizado, se añade al menú principal de informes, situado al lado del informe en el que se basa.

**Para crear un informe personalizado**

1. Ejecute un informe y configúrelo según sea necesario.
1. Haga clic en **[!UICONTROL Más]** > **[!UICONTROL Crear informe personalizado]**.
1. Especifique un nombre para el informe y, a continuación, haga clic en **[!UICONTROL Guardar]**.

   Asegúrese de que no haya repetido el nombre de otro informe ya existente.

>[!MORELIKETHIS]
>
>* [Personalización de menús](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/customize-menus.html)


## Seleccionar una fecha o un intervalo de fecha {#task_9BEF7D4D839A4748B76E8500D1406C34}

Instrucciones sobre cómo elegir los periodos de tiempo de los datos del informe.

<!-- 

t_reports_select_date.xml

 -->

Puede seleccionar días, semanas, meses o años específicos. También puede ejecutar informes de comparación.

Al abrir un tablero con informes breves que tengan distintos intervalos de fecha, puede elegir un nuevo intervalo de fecha en el calendario. Los cambios se aplicarán a todos los informes breves del tablero.

**Para seleccionar un intervalo de fecha**

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

Instrucciones sobre cómo usar el calendario para ejecutar comparaciones de fechas entre informes de clasificación.

<!-- 

t_reports_comparing_dates.xml

 -->

No puede comparar las fechas entre los informes de tendencia.

>[!NOTE]
>
>Si desea llevar a cabo una comparación por fechas en métricas clave en un panel, puede extraer los datos en el [Report Builder](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/home.translate.html) mediante dos solicitudes independientes. A continuación, puede usar fórmulas personalizadas en Excel para analizar la diferencia entre ambos.

Para comparar fechas entre informes de clasificación en Reports &amp; Analytics:

1. Ejecutar un informe.
1. Haga clic en el calendario en la parte superior.
1. Haga clic en **[!UICONTROL Comparar fechas]**.
1. Seleccione las fechas que desee utilizar.
1. Haga clic en **[!UICONTROL Ejecutar informe]**.

## Mostrar un porcentaje como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Instrucciones sobre cómo especificar si se quiere mostrar el porcentaje de una tabla de informe como un gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

Esta visualización también está disponible en informes breves de tableros.

1. Ejecute un informe compatible con porcentajes como, por ejemplo, un [!UICONTROL Informe de páginas].
1. Haga clic en **[!UICONTROL El porcentaje se muestra como: Gráfico]**.

## Normalizar datos de informes {#task_8005B55E59BD479DA67BC618FF8BC94A}

Instrucciones sobre cómo normalizar datos de informes.

<!-- 

t_reports_normalize.xml

 -->

Después de ejecutar un informe con fechas comparadas, o comparaciones A/B, puede normalizar los datos para mostrar el porcentaje de cambio entre los informes. El conjunto de datos secundarios se ajusta para compensar las diferencias en el número de días seleccionados o en los distintos volúmenes de tráfico.

**Para normalizar los datos de un informe**

1. Ejecute un informe que sea compatible con las comparaciones de fechas.
1. Haga clic en **[!UICONTROL Comparar fechas]** y, luego, especifique la comparación de fechas.
1. Haga clic en **[!UICONTROL Ejecutar informe]**.
1. Haga clic en **[!UICONTROL Normalizar datos: Sí]**.

## Seleccionar una página para un informe {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Instrucciones sobre cómo seleccionar una página concreta de entre las páginas del sitio web, para un informe.

<!-- 

t_reports_select_page.xml

 -->

1. Genere un informe, como por ejemplo un [!UICONTROL informe Vistas de página] (**[!UICONTROL Informes]** > **[!UICONTROL Métrica del sitio]** > **[!UICONTROL Vistas de páginas]**).
1. Haga clic en el vínculo **[!UICONTROL Página seleccionada]**.
1. En [!UICONTROL Elegir página], seleccione las páginas que desee mostrar.
1. Busque la página.
1. Haga clic en **[!UICONTROL Aceptar]**.

## Comparar grupos de informes {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Instrucciones sobre cómo mostrar informes de dos grupos de informes en el mismo informe.

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

**Para comparar grupos de informes**

1. Genere un informe que le permita comparar informes.
1. Haga clic en el vínculo **[!UICONTROL Comparar con otro sitio]**.
1. Busque el grupo de informes.
1. Haga clic en **[!UICONTROL Aceptar]**.

## Especificar la granularidad de los informes {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Instrucciones sobre cómo ver los totales de un informe: por horas, días, semanas, meses, trimestres o años.

<!-- 

t_reports_granularity.xml

 -->

El periodo de tiempo del informe determina qué opciones de granularidad se encuentran disponibles. Por ejemplo, puede elegir solo **[!UICONTROL Por hora]** si tiene un intervalo de tiempo de uno o dos días seleccionado. Solo puede seleccionar la granularidad **[!UICONTROL Por año]** si tiene más de un año seleccionado.

**Para especificar la granularidad del informe**

1. Genere un informe de tendencia como, por ejemplo, **[!UICONTROL Contenido del sitio]** > **[!UICONTROL Páginas]**.
1. Haga clic en el vínculo **[!UICONTROL Ver por]** y, a continuación, haga clic en una granularidad.

## Ejecutar un informe de día de la semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Instrucciones sobre cómo ejecutar informes en un día específico de la semana (por ejemplo, todos los lunes), en un intervalo de fecha determinado.

<!-- 

t_reports_day_of_week.xml

 -->

Esta función se aplica solamente a los informes de tendencia filtrados con un intervalo de fechas de semana o día.

1. Ejecute un informe de tendencias en un intervalo de fechas específico.
1. Haga clic en el vínculo **[!UICONTROL Día de la semana]** y, a continuación, haga clic en un día.

## Botón “Probar en el espacio de trabajo” {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Al hacer clic en el botón **[!UICONTROL Probar en el espacio de trabajo]** situado en la parte superior de un informe, el mismo informe se cargará en Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

Ahora, la mayoría de los informes de Reports &amp; Analytics incluyen un botón “Probar en el espacio de trabajo” que le permite reproducir la vista actual en Analysis Workspace para seguir personalizándola.

Actualmente, el botón solo está disponible si su nombre de usuario dispone de derechos completos con respecto a Analysis Workspace.

Si desea obtener más información sobre cómo puede personalizar su informe, consulte la guía de [Analysis Workspace](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html).
