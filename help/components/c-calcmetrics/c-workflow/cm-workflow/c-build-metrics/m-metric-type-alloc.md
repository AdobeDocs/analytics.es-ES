---
description: Si selecciona el icono de engranaje junto a una métrica, podrá especificar el tipo de métrica y el modelo de atribución.
title: Tipo de métrica y atribución
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Tipo de métrica y atribución

Si selecciona el icono de engranaje junto a una métrica, podrá especificar el tipo de métrica y el modelo de atribución.

* [Tipo de métrica](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modelo de atribución de columnas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018) ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Tipo de métrica {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Tipo de métrica | Definición |
|---|---|
| Estándar | Estas métricas son las mismas métricas utilizadas en los informes de [!DNL Analytics] estándares. Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a su contraparte de métricas no calculadas. Las métricas estándar son útiles para crear métricas calculadas específicas de cada elemento de línea individual. Por ejemplo, [Pedidos] / [Visitas] toma pedidos de ese elemento de línea en concreto y lo divide por el número de visitas de ese elemento de línea específico. |
| Total | Utilice el total del período de sistema de informes en cada elemento de línea. Si una fórmula consiste en una única métrica total, muestra el mismo número total en cada elemento de línea. Las métricas totales son útiles para crear métricas calculadas que se comparan con los datos totales del sitio. Por ejemplo, [Pedidos] / [Visitas totales] muestra la proporción de pedidos en comparación con TODAS las visitas de su sitio, no solo las visitas de una línea en concreto. |

## Modelo de atribución de columnas {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>En julio de 2018, [!DNL Analytics] introdujo [Attribution IQ](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/attribution.html), que revisaba la forma en que se evalúan los modelos de asignación en las métricas calculadas. Como parte de este cambio, las métricas calculadas que usan un modelo de asignación no predeterminado se migraron a los nuevos modelos de atribución mejorados:
>
>* Para obtener una lista completa de los modelos de atribución no predeterminados y de las ventanas retroactivas admitidas, consulte la documentación de IQ [de](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/attribution.html) atribución.
>* Los modelos de asignación “Último toque del canal de marketing” y “Primer toque del canal de marketing” se migrarán a los nuevos modelos de atribución “Último toque” y “Primer toque”, respectivamente. Tenga en cuenta que “Canales de marketing” no dejará de utilizarse, pues únicamente se retirarán los dos modelos de asignación que aparecen en las métricas calculadas.
>* Además, corregiremos la forma de calcular la asignación lineal. Para los clientes que usan métricas calculadas con modelos de asignación “Lineal”, los informes pueden cambiar ligeramente para reflejar el nuevo modelo de atribución corregido. Este cambio para métricas calculadas se reflejará en Analysis Workspace, Reports &amp; Analytics, API de informes, Report Builder y Ad Hoc Analysis. For more information, see **How Linear Allocation works (as of July 19, 2018**, below.
>



## Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018) 

En julio de 2018, Adobe cambió la forma en que se generan los informes de asignación lineal para métricas calculadas. Este cambio afecta a Analysis Workspace, Ad Hoc Analysis, Reports &amp; Analytics, Report Builder, Activity Map y las API de informes. Este cambio afectará principalmente a las eVars y otras dimensiones que tienen persistencia. Tenga en cuenta que estos cambios solo se aplicarán en las métricas calculadas y no tendrán ningún impacto en otros informes con asignación lineal (como el informe Páginas de Reports &amp; Analytics). Otros informes que utilicen la asignación lineal seguirán utilizando el método de asignación lineal existente.

El siguiente ejemplo ilustra cómo las métricas calculadas con asignación lineal cambiarán en el sistema de informes:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Visita individual 1 </th> 
   <th colname="col3" class="entry"> Visita individual 2 </th> 
   <th colname="col4" class="entry"> Visita individual 3 </th> 
   <th colname="col5" class="entry"> Visita individual 4 </th> 
   <th colname="col6" class="entry"> Visita individual 5 </th> 
   <th colname="col7" class="entry"> Visita individual 6 </th> 
   <th colname="col8" class="entry"> Visita individual 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datos enviados </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de último toque </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> PROMOCIÓN A </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> PROMOCIÓN B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de primer toque </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> PROMOCIÓN A </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN A </td> 
   <td colname="col6"> PROMOCIÓN A </td> 
   <td colname="col7"> PROMOCIÓN A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejemplo de prop </p> </td> 
   <td colname="col2"> PROMOCIÓN A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOCIÓN A </td> 
   <td colname="col5"> PROMOCIÓN B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, los valores A, B y C se enviaron a una variable en las visitas individuales 1, 3, 4 y 6 antes de que se realizara una compra de 10 $ en la visita individual 7. En la segunda fila, esos valores persisten entre visitas individuales en base a la visita de último toque. La tercera fila ilustra la persistencia de una visita de primer toque. Por último, la última fila ilustra cómo se registrarían los datos de una propiedad que no tenga persistencia.

## Funcionamiento de la asignación lineal antes de julio de 2018

Antes del 19 de julio de 2018, la atribución lineal se calculaba después de que ya se hubiera producido la persistencia del primer toque o del último toque. Esto significaba que para la eVar de último toque anterior, los $10 se distribuirían de la siguiente manera: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

Para la eVar de primer toque anterior, los $10 se entregarían a A. Para la prop: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, y C = 10 * (1/4) = $2,50. Para resumir la asignación lineal como funcionaba anteriormente:

| Valores | eVar de último toque actual | eVar de primer toque actual | Prop actual |
|---|---|---|---|
| PROMOCIÓN A | $5.00 | $10.00 | $5.00 |
| PROMOCIÓN B | $3.33 | 0 USD | $2.50 |
| PROMO C | $1.67 | 0 USD | $2.50 |
| Total | $10.00 | $10.00 | $10.00 |

**Resumen del funcionamiento de la asignación lineal desde el 19 de julio de 2018**

Después del 19 de julio, hemos corregido este comportamiento en las métricas calculadas. En lugar de usar los valores persistidos basados en el último o el primer toque, ahora [!DNL Analytics] usará solo los valores pasados (la primera fila de la tabla superior). Como tal, la configuración de asignación de dimensiones ya no afecta a la forma en que se calcula la asignación lineal (es decir, las propiedades y las eVars se tratarán de la misma manera) y los resultados reflejan lo que se pasó originalmente en lugar de los valores de primer o último toque que pueden haber persistido. Así pues, en los tres casos, A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, y C = 10 * (1/4) = $2,50.

| Valores | Nueva eVar de último toque | Nueva eVar de primer toque | Nueva propiedad |
|---|---|---|---|
| PROMOCIÓN A | $5.00 | $5.00 | $5.00 |
| PROMOCIÓN B | $2.50 | $2.50 | $2.50 |
| PROMO C | $2.50 | $2.50 | $2.50 |
| Total | $10.00 | $10.00 | $10.00 |

