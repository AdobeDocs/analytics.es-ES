---
description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
keywords: Fuente de datos;trabajo;métricas;columna previa;columna posterior;bots;filtro de fechas;cadena de eventos;común;fórmulas
seo-description: Se describe cómo calcular métricas habituales mediante fuentes de datos.
seo-title: Calcular métricas
solution: Analytics
title: Calcular métricas
topic: Reports and Analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# Calcular métricas

Se describe cómo calcular métricas habituales mediante fuentes de datos.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bots {#section_06753B95800F47668AAF52E7227F27C8}

Los bots se excluyen de las fuentes de datos en función de las [reglas de bots](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html) definidas para su grupo de informes.

## Filtro de fechas {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Para incluir filas del intervalo de fechas que desee, filtre el campo `date_time`. The `date_time` field is human readable (for example, `YYYY-MM-DD HH:MM:SS`) and is adjusted to the time zone of the report suite. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Cadena de eventos {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. Le recomendamos que lleve a cabo todo el procesamiento en `post_event_list` porque se eliminan los resultados duplicados y ya tiene lógica aplicada para eliminar eventos duplicados que tengan el mismo ID (consulte [Serialización de eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)).

Para que el ID de eventos conceda un nombre a las asignaciones, consulte la búsqueda de eventos que se suministra junto con su fuente de datos.

Para obtener más información sobre los eventos, consulte [Eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html).

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
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>Puede utilizar una lógica parecida para hacer un recuento de los vínculos personalizados: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> para contar vínculos personalizados. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> para contar los vínculos de descarga. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> para contar los vínculos de salida. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8, y 9 son filas de resumen cargadas mediante fuentes de datos. 7 representa las cargas de fuentes de datos del ID de transacción que no se deben incluir en los recuentos de visitas y de visitantes. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combinar <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>y <code> visit_start_time_gmt </code>*. Haga un recuento de la cantidad única de combinaciones. </li> 
    </ol> <p>*En casos excepcionales, por irregularidades de Internet o del sistema o el uso de ID de visitante personalizado, se pueden dar valores duplicados de <code> visit_num </code> para el mismo ID de visitante que no son la misma <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html"  >visita </a>. To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8, y 9 son filas de resumen cargadas mediante fuentes de datos. 7 representa las cargas de fuentes de datos del ID de transacción que no se deben incluir en los recuentos de visitas y de visitantes. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Búsqueda de la fuente de visitas </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combinar <code> post_visid_high </code> con <code> post_visid_low </code>. Haga un recuento de la cantidad única de combinaciones. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instancias de eventos </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>Por ejemplo: </p> 
    <code>
      post_event_list = 1,200 
    </code> <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. Son filas de resumen cargadas mediante fuentes de datos. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instancias de eVar </td> 
   <td colname="col2"> <p>Cuando se establece una eVar como una visita, <code> event_list </code> contiene una instancia de esa eVar. </p> <p>Por ejemplo: </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 
    </code> <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. Esto quiere decir que un valor de estas tres eVars se ha establecido como la visita. </p> <p>Para calcular las instancias para las eVars, utilice la misma lógica que se explica en la sección <i>Instancias de eventos</i> anterior, pero haga un recuento de la cantidad de veces que la búsqueda de eVars aparece en <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo empleado </td> 
   <td colname="col2"> <p>Para calcular el tiempo empleado, debe agrupar las visitas por visita y, a continuación, ordenarlas según el número de visitas en cada visita. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-page-event.md"  > page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Busca visitas en las que el valor que desea para realizar un seguimiento del tiempo empleado está configurado. Por ejemplo: 
      <code>
        hit&nbsp;1:&nbsp;post_prop1=red hit&nbsp;2:&nbsp;post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. Si el resultado es negativo, indica que la cantidad se recibió fuera del pedido y que el cálculo se debe rechazar. </li> 
    </ol> <p>Esta lógica se puede ampliar para calcular el tiempo empleado para otros valores. When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>Al informar acerca del tiempo empleado para un período específico, los Reports &amp; Analytics de marketing y los Ad Hoc Analysis evalúan las visitas más allá del período de informes para determinar el tiempo empleado para los valores dentro del período de informes, excepto si la fecha de inicio y/o finalización del período de tiempo se encuentra en un límite mensual. Debido a la complejidad de estos cálculos, puede que sea difícil que las métricas del tiempo empleado coincidan de forma exacta. El almacén de datos no evalúa las visitas más allá del período de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresos, pedidos, unidades </td> 
   <td colname="col2"> <p>Como el cambio de divisas se aplica al campo <code> post_product_list </code> en función de la configuración del grupo de informes, se recomienda utilizar esa columna. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 representan las filas de resumen cargadas mediante fuentes de datos. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Búsqueda de la fuente de visitas </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. This flag indicates that the purchase is a duplicate (meaning that a hit with the same <code> purchaseID </code> was already recorded). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p>El campo <code> post_product_list </code> utiliza la misma sintaxis que <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_products.html"  >s.products</a>, así que puede analizar esta cadena para calcular métricas. Por ejemplo: </p> 
      <code>
        ;Cross Trainers;1;69.95,;Athletic Socks;10;29.99 
      </code> <p>Al analizar esta cadena, puede determinar que se ha adquirido un par de zapatillas de cross ("cross trainers") por 69,95 USD y que los ingresos totales por esta compra han sido 99,94 USD. </p> </li> 
    </ol> <p>Nota: Analytics permite que los eventos de divisas que contienen ingresos se transmitan a través de la cadena de eventos. Por lo tanto, es posible que tenga que tener en cuenta los ingresos que no se encuentren en la cadena de productos. Consulte <i>Eventos numéricos o de divisas</i> en <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html"  >s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
