---
description: Pasos para ejecutar los distintos tipos de informes.
title: Ejecutar diferentes tipos de informes
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Ejecutar diferentes tipos de informes

Pasos para ejecutar los distintos tipos de informes.


## Ejecutar un informe de clasificación {#task_C570BA4A213F4F2EB7B30E012934BE7D}

En un informe de clasificación, la tabla muestra las clasificaciones de las páginas del informe en relación con la métrica, según el número o el porcentaje. Los informes de clasificación pueden mostrar varias métricas a la vez.

<!-- 

t_reports_ranked.xml

 -->

1. Genere un informe, como un [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. Para clasificar el informe, haga clic en un encabezado de columna de la tabla.

   Los informes de clasificación pueden tener hasta 200 artículos enumerados en la tabla (como productos, categorías, páginas web, etc.) y diez métricas (ingresos, pedidos, vistas, etc.).

## Ejecutar un informe de tendencias {#task_F03B4E760B9E4EA29FC3F654E6316887}

Los informes de tendencias muestran las métricas a lo largo del tiempo. Utilice este tipo de informe cuando desee ver cómo funciona un segmento de un período de tiempo al siguiente.

<!-- 

t_reports_trended.xml

 -->

La mayoría de los informes de conversión y tráfico tienen una vista de tendencias disponible. Con [!UICONTROL Calendar], puede mostrar la mejora de cualquier desglose de período de tiempo, incluidos los días de un mes, las semanas de un año, las semanas de un trimestre, los meses de un año, etc. Los informes de tendencias muestran las tendencias de una sola métrica (ingresos, pedidos, vistas, etc.) de hasta cinco elementos (como productos, categorías, páginas web, etc.).

**Para ejecutar un informe de tendencias**

1. Ejecute un informe de conversión o tráfico, como **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. En **[!UICONTROL Report Type]**, haga clic en **[!UICONTROL Trended.]**

## Ejecutar un informe de canales de conversión {#task_B926A74AA6A641138C2986C1635120CB}

Los informes de canal de conversión muestran el porcentaje de visitantes que avanzaron a través de un conjunto de eventos para realizar una acción deseada. Por ejemplo: puede ver cuántos visitantes avanzaron desde la visita a la página web, hasta la adición de artículos al carro y, a continuación, la compra de un artículo. Este informe también muestra el número de personas que se desviaron en el camino.

<!-- 

t_reports_conversion_funnel.xml

 -->

Para ejecutar este informe, seleccione un informe, como un informe Páginas ( **[!UICONTROL Reports]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** > **[!UICONTROL Campaign Conversion Funnel]**).

Consulte [Informes de conversión](https://marketing.adobe.com/resources/help/es_ES/reference/reports_conversion.html) para ver una descripción.

## Ejecutar un informe de visitas en el orden previsto {#task_8FD97C8260464F9DA731A93DB8F80184}

El [!UICONTROL Fallout Report] muestra el número de visitantes que visitaron una secuencia de páginas especificada previamente. También muestra las tasas de conversión y de visitas en el orden previsto entre cada paso.

<!-- 

t_reports_fallout.xml

 -->

Consulte el nuevo panel de Análisis [de](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/fallout_flow.html) visitas en el orden previsto en Espacio de trabajo de Análisis.

1. En [!UICONTROL Adobe Analytics], haga clic en **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. En la [!UICONTROL Fallout Report] página, haga clic en **[!UICONTROL Launch the Fallout Report Builder]**.

   ![Resultado](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. Haga clic en **[!UICONTROL Run Report]**.

   ![Resultado](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [Descripción del informe de visitas en el orden previsto](https://docs.adobe.com/content/help/es-ES/analytics/components/variables/dimensions-reports/reports-fallout.translate.html)


## Ejecutar un informe de flujo de página {#task_133E8B87C3F04DA0A42D10CBA499305B}

Los informes de flujo de página muestran el orden en que los visitantes acceden a las páginas y navegan por el sitio. Este informe ayuda a responder

Consulte la nueva visualización [Flujo](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/flow.html) en Análisis Workspace.

Ejecute un informe de [rutas](https://marketing.adobe.com/resources/help/es_ES/reference/reports_paths.html) .

Por ejemplo, haga clic en **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**.

![](assets/page_flow.png)

Este informe se lee de izquierda a derecha, comenzando por la página seleccionada. Las páginas que se vieron después de la página seleccionada se ilustran como una rama que se extiende hacia la derecha.

El porcentaje de cada página subsiguiente que se vio se muestra al lado del nombre de la página. El ancho de la línea conectada a cada página siguiente representa este porcentaje relativo.

**[!UICONTROL Path Views]**:: Indica el número de veces que se visitó una página, cuando se restringe a las rutas mostradas.

Por ejemplo: la página Política de privacidad podría tener un total de 10.000 vistas de página, pero sólo 500 de esas vistas de página se produjeron inmediatamente después de la Página de inicio. Por lo tanto, se utiliza el término vista de ruta.

El porcentaje relativo se representa con el ancho relativo de la línea. De manera predeterminada, este informe muestra cinco ramas de segundo nivel y cinco ramas de tercer nivel. Puede expandir el número de ramas para la vista hasta diez ramas de segundo nivel y cinco de tercer nivel. Al hacerlo, se aumenta la altura del informe y lo más probable es que sea necesario desplazarse para vista de todo el gráfico.

## Ejecutar un informe de canales {#task_2BBF6FACD48F479E8B2EE458919941CB}

Puede seleccionar eventos de éxito y agregarlos a un [!UICONTROL Purchase Conversion Funnel] informe o a un [!UICONTROL Product Conversion Funnel] informe.

<!-- 

t_reports_funnel.xml

 -->

1. Haga clic en **[!UICONTROL Reports]** > **[!UICONTROL Products]** > Canal [de conversión de productos](https://marketing.adobe.com/resources/help/es_ES/reference/reports_conversion_funnel.html).

## Ejecutar un informe de canal de marketing {#task_64ADED5CC75248319E06E3E029B47F78}

El sistema de informes de Canal de marketing proporciona un informe general de la asignación de canales de primer y último toque, con métricas de sistemas de informes estándar como ingresos, pedidos y costos. Estos informes le permiten analizar la cantidad de ingresos que genera cada canal.

<!-- 

t_reports_marketing_channel.xml

 -->

See the [Marketing Channel](https://marketing.adobe.com/resources/help/es_ES/mchannel/index.html) help system for more information.

## Ejecutar un informe de detección de anomalías {#task_4808C96327354D789C075823F5C3A049}

Describe cómo interpretar los gráficos de métricas individuales y de resumen en la detección de anomalías.

<!-- 

t_anomaly_view.xml

 -->

Consulte las nuevas funciones de [Detección de anomalías y Análisis de contribución](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/anomaly_detection.html) en Analysis Workspace.

**[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Anomaly Detection]** .

>[!NOTE] También puede ejecutar la Detección de anomalías desde proyectos de Analysis Workspace. [Más...](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/anomaly_detection.html)

Para obtener información sobre la configuración de la detección de anomalías, consulte la Guía de [referencia](https://marketing.adobe.com/resources/help/es_ES/sc/user/index.html#Setting_up_Anomaly_Detection).

La detección de anomalías muestra dos tipos de gráficos: Gráfico de resumen y gráficos de métricas individuales. Los gráficos de métricas individuales solo se muestran si se ha detectado al menos una anomalía para esa métrica.

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tipo de gráfico </p> </th> 
   <th colname="col2" class="entry"> <p>¿Qué hace? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gráfico de resumen </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">Cada cuadro representa una anomalía, rastreada por día, que corresponde a una métrica a continuación. </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">El verde indica anomalías por encima de la línea de tendencia, el azul por debajo de la línea de tendencia. </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">Indica la intensidad de la anomalía: Cuanto buena sea la anomalía, más oscuro será el color del punto de datos y más lejos estará de la línea de tendencia. </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">Al hacer clic en anomalías individuales, se coloca el gráfico de métricas individuales de esa anomalía (debajo del gráfico de resumen) en la parte superior. </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">Los valores de porcentaje de desviación (izquierda del gráfico) se calculan de la siguiente manera: 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">Si los límites superiores y el valor esperado son los mismos, el porcentaje de desviación es 100 % </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">De lo contrario, el porcentaje de desviación es ((valor actual - valor de límite superior) / (valor de límite superior - valor esperado)) * 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">Si el límite inferior y el valor esperado son el mismo, el porcentaje de desviación es -100% </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">De lo contrario, el porcentaje de desviación es ((valor de límite inferior - valor actual) / (valor actual - valor de límite inferior)) * -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">Al hacer clic en <span class="uicontrol">Mostrar segmentos</span>, aparece el carril del segmento que permite aplicar segmentos a un informe de detección de anomalías. <a href="https://marketing.adobe.com/resources/help/es_ES/analytics/segment/"  > Más información</a> sobre segmentación. </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">Al hacer clic en <span class="uicontrol">Editar métricas</span>, puede seleccionar y deseleccionar métricas para las cuales desea detectar anomalías. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gráfico de métricas individuales </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">Muestra puntos de datos anómalos para métricas de tendencias individuales (incluidas las métricas calculadas) como puntos. </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">Muestra la anomalía más reciente en la parte superior y, en segundo lugar, clasifica por número de anomalías. </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">Muestra una línea sólida para indicar los datos reales recopilados actualmente. Esto se compara con la previsión y el margen de error para determinar si los puntos de datos son anómalos. </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">Muestra una línea de puntos que representa una previsión basada en datos históricos (es decir, el período de prueba). </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">Muestra intervalos/límites de confianza del 95 % superior e inferior en una sombra gris. </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">Le permite contraer y expandir informes individuales haciendo clic en las flechas de doble hacia arriba o hacia abajo junto al nombre de la métrica. </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">Cambia el orden en que aparecen los gráficos de métricas al reaccionar a los desgloses en el informe de resumen (ver arriba) </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">Permite filtrar gráficos mediante términos de búsqueda, como "página", para todas las métricas relacionadas con la página. </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">Permite mostrar todas las métricas que haya definido o solo las que tengan anomalías. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configuración de la detección de anomalías {#task_AF347B34F56E44A6AE70E019B6EB2F08}

Pasos para seleccionar los grupos de informes, métricas y periodos de prueba/vista para la detección de anomalías.

<!-- 

t_anomaly_config.xml

 -->

La detección de anomalías se configura de forma independiente para cada grupo de informes.

1. Vaya a **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** .
1. Seleccione el grupo de informes para el cual desee realizar un seguimiento de la detección de anomalías diaria. Para mostrar una lista de grupos de informes, haga clic en el menú desplegable selector de grupos de informes.
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]** at the top right of the screen:  ![](assets/metrics_icon.png).

   Puede elegir las métricas de la lista (incluidas las métricas calculadas) de todas las métricas o de una lista de métricas con seguimiento. También puede filtrar por términos concretos para limitar la lista. 1. Once the report has been generated, define the **[!UICONTROL Training Period]** and the **[!UICONTROL View Period]** for anomaly detection. (Piense en el periodo de prueba como un &quot;periodo de aprendizaje&quot; para el algoritmo). 

   ![](assets/view_training_periods.png)

   Tenga en cuenta que:

* El período de prueba finaliza justo antes del inicio del período de vista.
* El valor predeterminado para ambos es de 30 días y se puede ampliar a 60 o 90 días.
* Al extender el período de prueba, los datos se sitúan en un contexto más amplio y puede reducir el tamaño de una anomalía.

   El informe Métricas de detección de anomalías se actualiza cada vez que se cambia un parámetro.
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   Consulte la [guía de segmentación de Analytics](https://marketing.adobe.com/resources/help/es_ES/analytics/segment/) para obtener más información sobre cómo crear y administrar segmentos. 1. (Opcional) Marque como favorito o añada un marcador al informe.
1. (Opcional) Cambiar la fecha de finalización del periodo de vista. La opción predeterminada es ayer.
1. Ahora puede empezar a interpretar el informe. [Visualización de gráficos de detección de anomalías](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049).

## Ejecutar un informe en tiempo real {#task_5D25929C918E40B18965222FA94176B0}

Describe cómo ver e interpretar los informes en tiempo real.

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]**.

sistema de informes en tiempo real oferta dos informes principales: un informe de descripción general y un informe detallado. Cada uno consiste en una serie de informes breves.

Para obtener información sobre la configuración de informes en tiempo real, consulte la Guía de referencia [de Analytics](https://marketing.adobe.com/resources/help/es_ES/reference/index.html#RealTime_Reports_Configuration).

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Componente de interfaz de usuario </th> 
   <th class="chdeschd"> Descripción </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleccionar grupo de informes</strong></td> 
   <td class="chdesc stentry"> Muestra el grupo de informes para abarca este informe en tiempo real. Para cambiar el grupo de informes, consulte la <a href="https://marketing.adobe.com/resources/help/es_ES/reference/t_realtime_admin.html"  >Configuración de informes en tiempo real </a>. </td> 
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
   <td class="chdesc stentry"> Los datos de la línea de tendencia azul muestran el tráfico total para el sitio en general. El eje X utiliza etiquetas literales (hace 15 minutos, hace 10 minutos) excepto el valor actual, que se muestra como una expresión en tiempo real. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve del total del sitio</strong></td> 
   <td class="chdesc stentry"> Presenta un recuento del total del sitio para la métrica seleccionada del informe en tiempo real durante los últimos N minutos. "N" se puede configurar mediante el selector Intervalo de tiempo. <p>El color y la dirección de la flecha se basan en el siguiente algoritmo: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Ganancia significativa (flecha arriba): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Ganancia (flecha arriba a la derecha): entre el 5 % y el 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Plano (flecha derecha): entre 5 % y -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Pérdida (flecha abajo derecha): entre -5% y -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Pérdida significativa (flecha abajo): &lt; -100% </li> 
      </ul> </p> <p>Si el total del sitio se informa en "instancias", estas instancias reflejan la dimensión en el informe breve principal. Si existe un nombre específico de la instancia (como "Vistas de página"), el total del sitio informa ese nombre. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve principal</strong></td> 
   <td class="chdesc stentry"> Informe de la dimensión principal del informe en tiempo real y de su métrica. Presenta una línea de tendencia para ese elemento en el intervalo de tiempo seleccionado. El total de la métrica representa la suma de toda la línea de tendencia. La flecha indica si el elemento está ganando, ganando, plano, perdiendo o perdiendo fuertemente. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Diálogo de búsqueda</strong></td> 
   <td class="chdesc stentry"> La búsqueda afecta a todos los informes breves. La búsqueda persiste a medida que se vista el informe. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ordenar por... Más popular/Ganadores/Perdedores</strong></td> 
   <td class="chdesc stentry"> Puede conmutar el orden entre <span class="uicontrol">Más popular</span> (predeterminado), <span class="uicontrol">Ganadores</span> (las dimensiones que muestran el mayor crecimiento) y <span class="uicontrol">Perdedores</span> (las dimensiones que están en trayectoria descendente). <p>Esta es la fórmula que se utiliza para determinar los ganadores y los perdedores: Tiempo real busca la muestra más temprana y la anterior a la muestra más reciente y realiza un sencillo cálculo de “% de cambio”. De modo que si se selecciona “Últimos 15 minutos” y n representa el minuto actual, n-1 se compara con n-15. Actualmente, Tiempo real no realiza ninguna ponderación. El minuto actual se ignora porque no está completo y probablemente produciría un cambio de % falso. </p> <p>Esta fórmula es coherente en todas las métricas utilizadas en el informe en tiempo real. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve 1 secundario</strong></td> 
   <td class="chdesc stentry"> Presenta informes en tiempo real para la dimensión del segundo informe aprovisionado y para la métrica. <p>El informe breve 1 secundario muestra las 4 categorías principales; el quinto es una agregación de todos los valores restantes. Para cada categoría se proporciona la vista total en bruto de esa categoría. Además, el total de todas las categorías se muestra en el centro. </p> <p> Al pasar el ratón sobre una sección se resalta la categoría asociada y se muestra la línea de tendencia de la categoría debajo de la rosca. </p> <p> Al pasar el ratón sobre un elemento de línea se resalta el elemento de línea más la sección asociada y se muestra la línea de tendencia de categoría debajo de la rosca. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Informe breve 2 secundario</strong></td> 
   <td class="chdesc stentry"> Presenta informes en tiempo real para la dimensión del tercer informe aprovisionado y para la métrica. Si pasa el ratón por encima de la etiqueta del elemento, la etiqueta se desliza a la derecha y se muestra una línea de tendencia para el elemento que se ha pasado por encima. </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **Informe breve de tendencia de elementos** | Presenta la línea de tendencia del elemento seleccionado en el informe Información general de los últimos N minutos. N se puede configurar mediante el selector Intervalo de tiempo. |
   |---|---|
   | **Informe breve total del elemento** | Presenta un recuento total de métricas del elemento seleccionado en el informe Información general de los últimos N minutos. N se puede configurar mediante el selector Intervalo de tiempo. |
   | **Informe breve 1 secundario correlacionado** | Este informe breve es muy similar al informe breve 1 secundario. La única diferencia es la fuente de datos utilizada para completar este informe: en este ejemplo, muestra la correlación (o desglose) entre una página específica (la que seleccionó en el informe breve principal del informe general) y las instancias vistas. |
   | **Informe breve 2 secundario correlacionado** | Este informe breve es muy similar al informe breve 2 secundario. La única diferencia es la fuente de datos utilizada para completar este informe: en este ejemplo, muestra la correlación (o desglose) entre una página específica (la que seleccionó en el informe breve principal del informe de resumen) y la dimensión de idioma. |
