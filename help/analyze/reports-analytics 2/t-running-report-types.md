---
description: Pasos para ejecutar los distintos tipos de informes.
title: Ejecutar diferentes tipos de informes
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 94%

---

# Ejecutar diferentes tipos de informes

{{ra-eol}}

Puede ejecutar muchos tipos diferentes de informes en Analysis Workspace. A continuación se muestran algunos ejemplos.

Para obtener una lista completa de los tipos de informes pregenerados disponibles, consulte [Uso de informes generados previamente](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## Ejecutar un informe de visitas en el orden previsto {#task_8FD97C8260464F9DA731A93DB8F80184}

El [!UICONTROL informe de visitas en el orden previsto] muestra el número de visitantes que visitaron una secuencia especificada previamente de páginas. También muestra la tasa de conversión y de visitas en el orden previsto entre cada paso.

Consulte el nuevo panel de [Análisis de visitas en el orden previsto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=es) de Analysis Workspace.

1. En [!UICONTROL Adobe Analytics], haga clic en **[!UICONTROL Informes]** > **[!UICONTROL Rutas]** > **[!UICONTROL Páginas]** > **[!UICONTROL Visita en el orden previsto]**.
1. En la página [!UICONTROL Informe de visitas en el orden previsto], haga clic en **[!UICONTROL Iniciar Report Builder para visitas en el orden previsto]**.

1. En la página [!UICONTROL Definir puntos de comprobación], especifique los puntos de comprobación que desee utilizar para el informe.
1. Haga clic en **[!UICONTROL Ejecutar informe]**.

## Ejecutar un informe de flujo de página {#task_133E8B87C3F04DA0A42D10CBA499305B}

Los informes de flujo de página muestran el orden en el que los visitantes acceden a las páginas y navegan a través del sitio. Este informe ayuda a dar respuesta

Por ejemplo, haga clic en **[!UICONTROL Workspace]** > **[!UICONTROL Informes]** > **[!UICONTROL Participación]** > **[!UICONTROL Flujo de página siguiente y anterior]**.

## Ejecutar un informe de canal de marketing {#task_64ADED5CC75248319E06E3E029B47F78}

La elaboración de informes de canal de marketing ofrece un informe con información general sobre la asignación del canal de primer y último toque, con métricas estándar de informes como ingresos, pedidos y costos. Estos informes permiten analizar cuántos ingresos genera cada canal.

Consulte el sistema de ayuda de [Canal de mercadotecnia](/help/components/c-marketing-channels/analyze-mc.md) para obtener más información.

## Ejecutar un informe de detección de anomalías {#task_4808C96327354D789C075823F5C3A049}

Puede ejecutar [Detección de anomalías y análisis de contribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=es) solo en Analysis Workspace.

## Ejecutar un informe en tiempo real {#task_5D25929C918E40B18965222FA94176B0}

Describe cómo ver e interpretar los informes en tiempo real.

**[!UICONTROL Informes > Métrica del sitio > Tiempo real]**.

Los informes en tiempo real ofrecen dos informes principales: un informe de descripción general y un informe detallado. Cada uno consiste en diversos informes breves.

Consulte [Resumen de informes en tiempo real](/help/components/c-real-time-reporting/realtime.md) para obtener más información.

1. Eche un vistazo al informe de **[!UICONTROL Información general]** y a sus componentes:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Componente de la interfaz de usuario </th> 
   <th class="chdeschd"> Descripción </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleccionar grupo de informes</strong></td> 
   <td class="chdesc stentry"> Muestra el grupo de informes para abarca este informe en tiempo real. Para cambiar el grupo de informes, consulte la <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html?lang=es"  >Configuración de informes en tiempo real </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Conmutar entre informes</strong></td> 
   <td class="chdesc stentry"> Le permite conmutar entre los informes que haya configurado (un máximo de 3). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleccionar intervalo de tiempo</strong></td> 
   <td class="chdesc stentry"> Le permite elegir el intervalo de tiempo general a usar en todos los informes cortos en el informe. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configurar informes</strong></td> 
   <td class="chdesc stentry"> Este vínculo de icono de engranaje solo es visible si tiene derechos de administrador. Si hace clic le lleva al administrador de grupos de informes en <span class="ignoretag"><span class="uicontrol">Herramientas del administrador</span> &gt; <span class="uicontrol">Grupos de informes</span> &gt; <span class="uicontrol">Editar la configuración</span> &gt; <span class="uicontrol">Tiempo real </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ver pantalla completa</strong></td> 
   <td class="chdesc stentry"> El icono de ver pantalla completa solo es visible si su monitor tiene una proporción de aspecto específica (16:9 o 16:10) y si su explorador es compatible. Tenga en cuenta que no puede interactuar con la pantalla mientras esté en modo pantalla completa (pulse <span class="uicontrol">Esc</span> para salir). El modo pantalla completa no agota el tiempo. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve del tráfico del sitio</strong></td> 
   <td class="chdesc stentry"> Los datos de la línea de tendencia azul muestran el tráfico total de todo el sitio. El eje X usa etiquetas literales (Hace 15 minutos, Hace 10 minutos) excepto para el valor actual, el cual se muestra como expresión en tiempo real. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve del total del sitio</strong></td> 
   <td class="chdesc stentry"> Presenta un recuento del total del sitio para la métrica seleccionada de los informes en tiempo real de los últimos N minutos. "N" se puede configurar mediante el selector de intervalo de tiempo. <p>El color de la flecha y su dirección se basan en el siguiente algoritmo: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Aumento significativo (flecha arriba): &gt; 100 % </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Aumento (flecha arriba a la derecha): entre 5 % y 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Estable (flecha derecha): entre 5 % y -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Pérdida (flecha abajo a la derecha): entre -5 % y -100 % </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Pérdida significativa (flecha abajo): &lt; -100 % </li> 
      </ul> </p> <p>Si se generan informes del total del sitio en "instancias", estas instancias reflejan la dimensión del informe breve primario. Si ya existe un nombre específico para la instancia (como "Vistas de página"), el total del sitio indica este nombre. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve principal</strong></td> 
   <td class="chdesc stentry"> Informe de la dimensión principal del informe en tiempo real y de su métrica. Presenta una línea de tendencia de este elemento para el intervalo de tiempo seleccionado. El total de la métrica representa la suma de toda la línea de tendencia. La flecha indica si el elemento está aumentando significativamente, aumentando, estable, perdiendo o perdiendo significativamente. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Diálogo de búsqueda</strong></td> 
   <td class="chdesc stentry"> La búsqueda influye en todos los informes breves. La búsqueda se mantiene mientras ve el informe. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ordenar por... Más popular/Ganadores/Perdedores</strong></td> 
   <td class="chdesc stentry"> Puede conmutar el orden entre <span class="uicontrol">Más popular</span> (predeterminado), <span class="uicontrol">Ganadores</span> (las dimensiones que muestran el mayor crecimiento) y <span class="uicontrol">Perdedores</span> (las dimensiones que están en trayectoria descendente). <p>Esta es la fórmula que se utiliza para determinar los ganadores y los perdedores: Tiempo real busca la muestra más temprana y la anterior a la muestra más reciente y realiza un sencillo cálculo de “% de cambio”. De modo que si se selecciona “Últimos 15 minutos” y n representa el minuto actual, n-1 se compara con n-15. Tiempo real actualmente no realiza ninguna ponderación. El minuto actual se ignora porque no está completo y probablemente produciría un cambio de porcentaje falso. </p> <p>Esta formula se mantiene entre todas las métricas utilizadas en el informe en tiempo real. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve 1 secundario</strong></td> 
   <td class="chdesc stentry"> Presenta los informes en tiempo real para la dimensión del segundo informe aprovisionado y la métrica. <p>El informe breve 1 secundario muestra las 4 categorías principales, la quinta es una suma de los valores restantes. Para cada categoría, se proporciona la vista en bruto total de esa categoría. Además, se muestra el total de todas las categorías en el centro. </p> <p> Si pasa el ratón por encima de una sección se destaca la categoría asociada y muestra la línea de tendencia de la categoría debajo de la rosca. </p> <p> Si pasa el ratón por encima de un elemento de línea se destaca el elemento de línea y la sección asociada y muestra la línea de tendencia de la categoría debajo de la rosca. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve 2 secundario</strong></td> 
   <td class="chdesc stentry"> Presenta los informes en tiempo real para la dimensión del tercer informe aprovisionado y la métrica. Si pasa el ratón por encima de la etiqueta del elemento, se desliza la etiqueta a la derecha y muestra una línea de tendencia para el elemento sobre el que ha colocado el puntero. </td> 
   </tr> 
   </table>

2. Haga clic en un elemento de la lista en el Informe breve principal para iniciar la vista **[!UICONTROL Detalles]** para dicho elemento de lista:  ![](assets/rtr_detail_report.png)

   | **Informe breve de tendencia del elemento** | Presenta la línea de tendencia del elemento que se ha seleccionado en el informe de descripción general de los últimos N minutos. N se puede configurar mediante el selector de intervalo de tiempo. |
   |---|---|
   | **Informe breve total del elemento** | Presenta un recuento de la métrica total del elemento que se ha seleccionado en el informe de descripción general de los últimos N minutos. N se puede configurar mediante el selector de intervalo de tiempo. |
   | **Informe breve 1 secundario correlacionado** | Este informe breve es muy similar al informe breve 1 secundario. La única diferencia es la fuente de datos utilizada para completar el informe: en este ejemplo, muestra la correlación (o desglose) entre una página específica (la que ha seleccionado en el informe breve principal del informe de descripción general) y las instancias vistas. |
   | **Informe breve 2 secundario correlacionado** | Este informe breve es muy similar al informe breve 2 secundario. La única diferencia es la fuente de datos utilizada para completar el informe: en este ejemplo, muestra la correlación (o desglose) entre una página específica (la que ha seleccionado en el informe breve principal del informe de descripción general) y la dimensión del idioma. |
