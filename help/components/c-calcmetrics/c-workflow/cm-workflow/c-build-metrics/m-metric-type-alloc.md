---
description: Si selecciona el icono de engranaje junto a una métrica, puede especificar el tipo de métrica y el modelo de atribución.
seo-description: Si selecciona el icono de engranaje junto a una métrica, puede especificar el tipo de métrica y el modelo de atribución.
seo-title: Tipo de métrica y atribución
title: Tipo de métrica y atribución
uuid: 64649698-df 2 a -42 c 3-bb 31-938 f 766 e 1 d 1 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tipo de métrica y atribución

Si selecciona el icono de engranaje junto a una métrica, puede especificar el tipo de métrica y el modelo de atribución.

* [Tipo de métrica](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modelo de atribución de columnas](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Tipo de métrica {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Tipo de métrica | Definición |
|---|---|
| Estándar | These metrics are the same metrics used in standard [!DNL Analytics] reporting. Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a los de su métrica no calculada homóloga. Las métricas estándar son útiles para crear métricas calculadas específicas para cada elemento de línea individual. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item. |
| Total | Utilice el total para el periodo de generación de informes de cada elemento de línea. Si una fórmula consiste en una única métrica total, muestra el mismo número total en cada elemento de línea. Las métricas totales son útiles para crear métricas calculadas que se comparan con los datos totales del sitio. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item. |

## Modelo de atribución de columnas {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>In July 2018, [!DNL Analytics] introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. Como parte de este cambio, las métricas calculadas que usan un modelo de asignación no predeterminado se migraron a los nuevos modelos de atribución mejorados:
>
>* Para obtener una lista completa de todos los modelos de atribución no predeterminados y ventanas retroactivas, consulte la documentación de [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html).
>* Los modelos de asignación “Último toque del canal de marketing” y “Primer toque del canal de marketing” se migrarán a los nuevos modelos de atribución “Último toque” y “Primer toque”, respectivamente. Tenga en cuenta que “Canales de marketing” no dejará de utilizarse, pues únicamente se retirarán los dos modelos de asignación que aparecen en las métricas calculadas.
>* Además, corregiremos la forma de calcular la asignación lineal. Para los clientes que usan métricas calculadas con modelos de asignación “Lineal”, los informes pueden cambiar ligeramente para reflejar el nuevo modelo de atribución corregido. This change to calculated metrics will be reflected in Analysis Workspace, [!UICONTROL Reports &amp; Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. Para obtener más información, consulte [Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).
>



## Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018) {#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

En julio de 2018, Adobe cambió la forma en que se informa la asignación lineal para Métricas calculadas. This change impacts Analysis Workspace, Ad Hoc Analysis, [!UICONTROL Reports &amp; Analytics], Report Builder, Activity Map, and the Reporting APIs. Este cambio afectará principalmente a las eVars y otras dimensiones que tienen persistencia. Note that these changes will only apply to calculated metrics and will not impact other reports using linear allocation (such as the Pages report in [!UICONTROL Reports &amp; Analytics]). Los otros informes que usan la asignación lineal seguirán usando el método existente.

El ejemplo siguiente ilustra de qué forma cambiarán las métricas calculadas con la asignación lineal en los informes:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Visita 1 </th> 
   <th colname="col3" class="entry"> Visita 2 </th> 
   <th colname="col4" class="entry"> Visita 3 </th> 
   <th colname="col5" class="entry"> Visita 4 </th> 
   <th colname="col6" class="entry"> Visita 5 </th> 
   <th colname="col7" class="entry"> Visita 6 </th> 
   <th colname="col8" class="entry"> Visita 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datos recibidos </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMOCIÓN C </td> 
   <td colname="col8"> 10 USD </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de último toque </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> PROMOCIÓN A </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> PROMOCIÓN B </td> 
   <td colname="col7"> PROMOCIÓN C </td> 
   <td colname="col8"> 10 USD </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de primer toque </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> PROMOCIÓN A </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN A </td> 
   <td colname="col6"> PROMOCIÓN A </td> 
   <td colname="col7"> PROMOCIÓN A </td> 
   <td colname="col8"> 10 USD </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prop de ejemplo </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMOCIÓN C </td> 
   <td colname="col8"> 10 USD </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, los valores A, B y C se han enviado a una variable en las visitas 1, 3, 4 y 6 antes de realizarse una compra de 10 USD en la visita 7. En la segunda fila, estos valores persisten a lo largo de las visitas con base en una visita de último toque. La tercera fila ilustra una persistencia de visita de primer toque. Finalmente, la última fila ilustra de qué forma se registrarán los datos para una prop que no tiene persistencia.

**Resumen del funcionamiento de la asignación lineal antes de julio de 2018**

Antes del 19 de julio de 2018, la atribución lineal se calculaba después de producirse la persistencia de primer toque o de último toque. Esto quiere decir que, para la última eVar de toque anterior, 10 $ se distribuirían de esta forma: A = 10 * (3/6) = 5 $, B = 10 * (2/6) = 3,33 $, C = 10 * (1/6) = 1,67 $.

Para la eVar de primer toque anterior, los 10 $ se asignarían a A. Para la prop: A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $ y C = 10 * (1/4) = 2,50 $. Para resumir el funcionamiento anterior de la asignación lineal:

| Valores | eVar de último toque actual | eVar de primer toque actual | Prop actual |
|---|---|---|---|
| PROMOCIÓN A | 5,00 USD | 10,00 USD | 5,00 USD |
| PROMOCIÓN B | 3,33 USD | 0 USD | 2,50 USD |
| PROMOCIÓN C | 1,67 USD | 0 USD | 2,50 USD |
| Total | 10,00 USD | 10,00 USD | 10,00 USD |

**Resumen del funcionamiento de la asignación lineal a partir del 19 de julio de 2018**

Después del 19 de julio, corregimos este comportamiento en las métricas calculadas. Instead of using the persisted values based on last touch or first touch, [!DNL Analytics] now uses only the values that were passed in (the first row of the top table). De este modo, la configuración de la asignación de dimensiones ya no tendrá ningún impacto en la forma de calcular la asignación lineal (lo que significa que props y eVars se tratarán del mismo modo) y los resultados reflejarán lo que se haya transferido originalmente, en lugar de los valores de primer o último toque que puedan haber persistido. Es decir, en los tres casos, A = 10 * (2/4) = 5 USD, B = 10 * (1/4) = 2,50 USD, and C = 10 * (1/4) = 2,50 USD.

| Valores | eVar de último toque nueva | eVar de primer toque nueva | Prop nueva |
|---|---|---|---|
| PROMOCIÓN A | 5,00 USD | 5,00 USD | 5,00 USD |
| PROMOCIÓN B | 2,50 USD | 2,50 USD | 2,50 USD |
| PROMOCIÓN C | 2,50 USD | 2,50 USD | 2,50 USD |
| Total | 10,00 USD | 10,00 USD | 10,00 USD |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

