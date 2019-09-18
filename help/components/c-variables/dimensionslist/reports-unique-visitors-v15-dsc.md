---
description: Muestra el número de visitantes únicos que accedieron al sitio web. Cada visitante se cuenta solamente una vez, independientemente de cuántas veces haya visitado el sitio web.
seo-description: Muestra el número de visitantes únicos que accedieron al sitio web. Cada visitante se cuenta solamente una vez, independientemente de cuántas veces haya visitado el sitio web.
seo-title: Visitantes únicos
solution: Analytics
title: Visitantes únicos
topic: Informes
uuid: e70e1a14-b3b9-4d1a-a8a5-a247a443c752
translation-type: tm+mt
source-git-commit: 646d6e01d0f0201c78117ee9bf9ff64fda9a026a

---


# Visitantes únicos

Muestra el número de visitantes únicos que accedieron al sitio web. Cada visitante se cuenta solamente una vez, independientemente de cuántas veces haya visitado el sitio web.

**Datos de muestra**

Consulte la tabla siguiente para los ejemplos de esta página. Aquí se representa el mismo visitante:

<table id="table_4F54873A4ED8451494E466C2BDB15B00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> 1/1/2017 </th> 
   <th colname="col3" class="entry"> 1/1/2017 </th> 
   <th colname="col4" class="entry"> 1/2/2017 </th> 
   <th colname="col5" class="entry"> 1/2/2017 </th> 
   <th colname="col6" class="entry"> 1/2/2017 </th> 
   <th colname="col7" class="entry"> 1/3/2017 </th> 
   <th colname="col8" class="entry"> 1/4/2017 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Página </p> </td> 
   <td colname="col2"> <p>A </p> </td> 
   <td colname="col3"> <p>C </p> </td> 
   <td colname="col4"> <p>A </p> </td> 
   <td colname="col5"> <p>B </p> </td> 
   <td colname="col6"> <p>C </p> </td> 
   <td colname="col7"> <p>D </p> </td> 
   <td colname="col8"> <p>E </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar </p> </td> 
   <td colname="col2"> <p>T, U </p> </td> 
   <td colname="col3"> <p>V </p> </td> 
   <td colname="col4"> <p>W </p> </td> 
   <td colname="col5"> <p> </p> </td> 
   <td colname="col6"> <p>X, Y </p> </td> 
   <td colname="col7"> <p>Z </p> </td> 
   <td colname="col8"> <p>Z </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informe de visitantes únicos - Métrica de tendencias {#section_372C08A881D34BBF811C1DE0A1460617}

[!UICONTROL Los informes de visitantes] únicos se comportan de manera similar en los análisis específicos. Para cada entrada en la que se produzca la visita, el visitante se contabiliza en esa entrada. Cada página recibe el crédito si el visitante está en esa página.

<table id="table_7D9119045E8243698B6BB2E8C93F6B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Además, cada fecha recibe crédito por tener a ese visitante en dicha fecha.

<table id="table_E0D06D9434444947BDA818F61A580B65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL Informe de visitantes únicos]desglosado por *`Page`*.**

Puede seleccionar una página para el [!UICONTROL informe de visitantes únicos]. En el informe siguiente, el visitante visita la página A en estas fechas:

<table id="table_2ABA17B19E0D4F92AAB003BE784DA9E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visitantes únicos basados en períodos (tendencias) {#section_B3502EBF1ACB487AA8E0EFBA9A0561FD}

Puede ejecutar [!UICONTROL informes de visitantes únicos] por hora, diarios, semanales, mensuales, trimestrales y anuales (tendencias).

Los visitantes únicos basados en períodos se contabilizan únicamente en la primera visita del período especificado. Por ejemplo, los visitantes únicos por hora se contabilizan en la primera visita que se produzca durante la hora especificada. Los visitantes únicos diarios se contabilizan en la primera visita del día especificado.

<table id="table_FF14F05CDFDA4F2E92A62D9D751A1CAA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanales </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

El siguiente informe se mostraría para los visitantes únicos diarios.

<table id="table_4E44BC4722064501A5B648BE80ED8E60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos diarios </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>4 </p> </td> 
  </tr> 
 </tbody> 
</table>

Los totales de las métricas pueden variar en función del intervalo de fechas del informe. Los informes de marketing comienzan a contabilizar los visitantes únicos basados en períodos a partir del inicio del intervalo de fechas. Por ejemplo, si el intervalo de fechas es del 2 de enero hasta el 3 de enero, se mostrarían los resultados siguientes para los visitantes únicos semanales:

<table id="table_B695708BB22949E7BA293FE492D2EEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanales </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Segmentación**

Puede utilizar la segmentación para modificar el intervalo de fechas con el objetivo de incluir fechas posteriores en vez de fechas anteriores. Por ejemplo: tomemos el intervalo de fechas anterior del 2 de enero al 3 de enero (tal como se muestra en la tabla anterior). Si se aplica un segmento en el que Página = C, 2 de enero no pasaría el segmento y la primera entrada del informe de visitante único semanal se produciría el 3 de enero. Si En cambio se aplica un segmento en el que Página = D, entonces tanto el 2 de enero como el 3 de enero quedarían excluidos. Visitante único semanal no mostraría ningún resultado y quedaría excluido del total.

**Informes de visitantes únicos basados en períodos **

Estos informes utilizan una página, una prop y un atributo concretos (ejemplo: donde Página = A).

Supongamos que crea una tendencia del [!UICONTROL informe de páginas] con una métrica Visitante único basada en períodos. Si hay un desglose o una variable seleccionados para los informes Visitantes únicos basados en períodos, los informes de marketing contabilizarán todas las instancias únicas del visitante y del par de atributos. El procesamiento para la primera entrada del visitante no es diferente a los ejemplos anteriores. En las entradas subsiguientes, estos informes incluyen las entradas que los informes anteriores no incluyen, si la página es diferente.

Para los visitantes únicos semanales, en los que Página = A, los informes de marketing excluyen el 2 de enero de los totales. Se aplica esta exclusión porque los informes de marketing ya han contabilizado al visitante único semanal el 1 de enero. A continuación se muestra un informe de visitantes únicos semanales donde Página = A:

<table id="table_9C5E00029C7340B28D76696E84F66511"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanales </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Para visitantes únicos semanales, donde Página = B, la única fecha en la que se produce es el 2 de enero, tal como se muestra aquí:

<table id="table_262150BECCB74120B58F506F4BC6F629"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Visitas - Visitantes únicos semanales </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas de visitante único basado en períodos en informes sin tendencias {#section_90B784F4E49F4930B3F0923B95958BA2}

Puede agregar métricas de visitante único basado en períodos a informes sin tendencias como, por ejemplo, una métrica de visitantes únicos semanales en un [!UICONTROL informe de páginas].

<table id="table_8651A42696B0404CAEAE0FC5522CC1C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col02" class="entry"> Fecha de visita </th> 
   <th colname="col2" class="entry"> Visitas - Visitante único semanal </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col02"> <p>5 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col02"> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Una métrica de visitantes únicos diarios en un [!UICONTROL informe de páginas] mostraría:

<table id="table_04C7C305C2B945D6A79A6B80F48A4BF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col02" class="entry"> Fecha de visita </th> 
   <th colname="col2" class="entry"> Visitas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>1 de enero </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>2 de enero </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>3 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>4 de enero </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col02"> <p> </p> </td> 
   <td colname="col2"> <p>4 visitantes únicos diarios </p> </td> 
  </tr> 
 </tbody> 
</table>

Para desglosar un atributo en otro (por ejemplo, *`page`* by *`eVar`*), Analytics allocates a period-based Unique Visitor for each unique instance of the period and page (or the attribute being correlated).

Si desglosa la Página Page A en las eVars T, U, el 2 de enero quedará excluido porque la Página A se visualizó el 1 de enero. Los siguientes resultados se mostrarían para los visitantes únicos semanales.

<table id="table_328A6F2E920A44B3B55A6E6A630F6DBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanales </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>T </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>U </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookies persistentes {#section_81E139F08AEB4E30A06472856975EA1E}

Las cookies persistentes permanecen en el equipo de un visitante entre visitas para que Adobe pueda identificar a visitantes en visitas siguientes. To see the percentage of users who do and do not accept persistent cookies, select **[!UICONTROL Filter]** &gt; **[!UICONTROL Persistent Cookies]**.

El gráfico al igual que la vista de detalles más abajo muestran tanto visitantes de cookies persistentes como visitantes de cookies no persistentes. Muy a menudo, el número de visitantes de cookies no persistentes es ínfimo.
