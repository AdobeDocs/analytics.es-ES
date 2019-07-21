---
description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
keywords: Fuente de datos; trabajo; métricas; pre column; post column; bots; filtros de fecha; event string; common; fórmulas
seo-description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
seo-title: Calcular métricas
solution: Analytics
title: Calcular métricas
topic: Reports and Analytics
uuid: a 45 ea 5 bb -7 c 83-468 f-b 94 a -63 add 78931 d 7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Calcular métricas

Se describe cómo calcular métricas habituales mediante fuentes de datos.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bots {#section_06753B95800F47668AAF52E7227F27C8}

Los bots se excluyen de las fuentes de datos en función de las [reglas de bots](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules) definidas para su grupo de informes.

## Filtro de fechas {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Para incluir filas del intervalo de fechas que desee, filtre el campo `date_time`. `date_time` El campo es legible para humanos (por ejemplo `YYYY-MM-DD HH:MM:SS`,) y se ajusta a la zona horaria del grupo de informes. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Cadena de eventos {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. Le recomendamos que lleve a cabo todo el procesamiento en `post_event_list` porque se eliminan los resultados duplicados y ya tiene lógica aplicada para eliminar eventos duplicados que tengan el mismo ID (consulte [Serialización de eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization)).

Para que el ID de eventos conceda un nombre a las asignaciones, consulte la búsqueda de eventos que se suministra junto con su fuente de datos.

Para obtener más información sobre los eventos, consulte [Eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events).

## Fórmulas para las métricas habituales {#section_E26A01C234484857BF8C74443222AE41}

En la tabla siguiente encontrará las instrucciones para calcular varias métricas habituales.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Cómo hacer el cálculo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Vistas de páginas </td> 
   <td colname="col2"> <p> Las vistas de páginas pueden calcularse contando cuándo hay un valor en <code>post_pagename</code> o en <code>post_page_url </code>. </p> 
    <p>Puede utilizar una lógica parecida para hacer un recuento de los vínculos personalizados: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100</code> para hacer un recuento de los vínculos personalizados. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101</code> para hacer un recuento de los vínculos de descarga. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102</code> para hacer un recuento de los vínculos de salida. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Excluya todas las filas en las que <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Excluya todas las filas con <code>hit_source = 5,7,8,9 </code>. 5, 8, y 9 son filas de resumen cargadas mediante fuentes de datos. 7 representa las cargas de fuentes de datos del ID de transacción que no se deben incluir en los recuentos de visitas y de visitantes. Consulte <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combine <code>post_visid_high</code>, <code>post_visid_low</code>, <code>visit_num</code> y <code>visit_start_time_gmt </code>*. Haga un recuento de la cantidad única de combinaciones. </li> 
    </ol> <p>*En casos excepcionales, por irregularidades de Internet o del sistema o el uso de ID de visitante personalizado, se pueden dar valores duplicados de <code>visit_num</code> para el mismo ID de visitante que no son la misma <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external">visita </a>. Para evitar los problemas resultantes, incluya también <code>visit_start_time_gmt</code> al hacer el recuento de visitas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Excluya todas las filas en las que <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Excluya todas las filas con <code>hit_source = 5,7,8,9 </code>. 5, 8, y 9 son filas de resumen cargadas mediante fuentes de datos. 7 representa las cargas de fuentes de datos del ID de transacción que no se deben incluir en los recuentos de visitas y de visitantes. Consulte <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Búsqueda de la fuente de visitas </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combine <code>post_visid_high</code> y <code>post_visid_low </code>. Haga un recuento de la cantidad única de combinaciones. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instancias de eventos </td> 
   <td colname="col2"> <p>Cuando un evento se ha establecido en una visita, <code>post_event_list</code> contiene el evento. Se eliminan los duplicados del campo <code>post_event_list</code>, y se recomienda determinar las instancias de eventos. </p> <p>Por ejemplo: </p> 
    <code>post_ event_ list = 1.200 </code>
  <p>Indica una instancia de <code>purchase</code> y <code>event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Excluya todas las filas en las que <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Excluya todas las filas con <code>hit_source = 5,8,9 </code>. Son filas de resumen cargadas mediante fuentes de datos. Consulte <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Haga un recuento de la cantidad de veces que el valor de la búsqueda de eventos aparece en <code>post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instancias de eVar </td> 
   <td colname="col2"> <p>Cuando se establece una eVar como una visita, <code>event_list</code> contiene una instancia de esa eVar. </p> <p>Por ejemplo: </p> 
    <code>post_ event_ list &amp; amp; nbsp; = &amp; amp; nbsp; 100,101,106 </code>
  <p>Indica una instancia de <code>eVar1</code>, <code>eVar2</code> y <code>eVar7 </code>. Esto quiere decir que un valor de estas tres eVars se ha establecido como la visita. </p> <p>Para calcular las instancias para las eVars, utilice la misma lógica que se explica en la sección <i>Instancias de eventos</i> anterior, pero haga un recuento de la cantidad de veces que la búsqueda de eVars aparece en <code>post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo empleado </td> 
   <td colname="col2"> <p>Para calcular el tiempo empleado, debe agrupar las visitas por visita y, a continuación, ordenarlas según el número de visitas en cada visita. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Excluya todas las filas en las que <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Agrupar visitas para una visita mediante la concatenación de <code>visid_high</code>, <code>visid_low</code> y <code>visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Ordenar visitas para cada visita por <code>visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Busca visitas en las que el valor que desea para realizar un seguimiento del tiempo empleado está configurado. Por ejemplo: 
      <code>visita 1: post_ prop 1 = red hit 2: post_ prop 1 = blue </code>
  </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Resta <code>post_cust_hit_time</code> para la visita 1 de <code>post_cust_hit_time</code> para la visita 2 para determinar los segundos entre estas dos visitas. El resultado es el tiempo empleado para <code>post_prop1=red </code>. Si el resultado es negativo, indica que la cantidad se recibió fuera del pedido y que el cálculo se debe rechazar. </li> 
    </ol> <p>Esta lógica se puede ampliar para calcular el tiempo empleado para otros valores. Al calcular el tiempo empleado, Analytics calcula el tiempo empleado según el tiempo en que se estableció el valor en una llamada de <code>seguimiento</code> (<code>page_event=0</code>) o <code>trackLink</code> (<code>page_event=10|11|12</code>), hasta el momento de la siguiente vista de página (llamada de <code>seguimiento</code>). </p> <p>Al informar acerca del tiempo empleado para un período específico, los Reports &amp; Analytics de marketing y los Ad Hoc Analysis evalúan las visitas más allá del período de informes para determinar el tiempo empleado para los valores dentro del período de informes, excepto si la fecha de inicio y/o finalización del período de tiempo se encuentra en un límite mensual. Debido a la complejidad de estos cálculos, puede que sea difícil que las métricas del tiempo empleado coincidan de forma exacta. El almacén de datos no evalúa las visitas más allá del período de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresos, pedidos, unidades </td> 
   <td colname="col2"> <p>Como el cambio de divisas se aplica al campo <code>post_product_list</code> en función de la configuración del grupo de informes, se recomienda utilizar esa columna. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Excluya todas las filas en las que <code>exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Excluya todas las filas con <code>hit_source = 5,8,9 </code>. 5-9 representan las filas de resumen cargadas mediante fuentes de datos. Consulte <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignorar datos de compra para filas en las que <code>duplicate_purchase = 1 </code>. Este indicador indica que la compra es un duplicado (lo que significa que ya se registró una visita con el mismo <code>ID de compra</code>). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p>El campo <code>post_product_list</code> utiliza la misma sintaxis que <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external">s.products</a>, así que puede analizar esta cadena para calcular métricas. Por ejemplo: </p> 
      <code>; Cross Developers; 1; 69.95; Calcetines deportivos; 10; 29,99 </code>
  <p>Al analizar esta cadena, puede determinar que se ha adquirido un par de zapatillas de cross ("cross trainers") por 69,95 USD y que los ingresos totales por esta compra han sido 99,94 USD. </p> </li> 
    </ol> <p>Nota: Analytics permite que los eventos de divisas que contienen ingresos se transmitan a través de la cadena de eventos. Por lo tanto, es posible que tenga que tener en cuenta los ingresos que no se encuentren en la cadena de productos. Consulte <i>Eventos numéricos o de divisas</i> en <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external">s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
