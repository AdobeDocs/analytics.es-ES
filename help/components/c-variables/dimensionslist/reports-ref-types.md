---
description: Al realizar un seguimiento y registrar los sitios referentes de los visitantes permite averiguar, cómo descubrió el sitio el visitante en cada visita.
title: Tipo de referente
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tipo de referente

Al realizar un seguimiento y registrar los sitios referentes de los visitantes permite averiguar, cómo descubrió el sitio el visitante en cada visita.

La lista siguiente define los distintos tipos de referentes:

**Otros sitios web**: los referentes se registran cuando el visitante hace clic en un vínculo en una página de otro sitio web (no definida como parte de su sitio) y llega a su sitio web.

**Motores de búsqueda**: Los referentes de motor de búsqueda se registran cuando los visitantes usan un motor de búsqueda para acceder a su sitio. Adobe debe considerar el valor de referencia como un motor de búsqueda, y no puede tratarse de un subdominio que no se considere como tal (por ejemplo, [!DNL mail.yahoo.com] no es un motor de búsqueda porque corresponde al dominio de Gmail).

**[!UICONTROL Redes sociales]**: Adobe debe considerar el valor de referencia como una red social. Consulte [Lista de redes sociales](https://helpx.adobe.com/es/analytics/kb/list-social-networks.html).

**Correo electrónico**: Un dominio de referencia se considera un dominio de referencia de correo electrónico cuando los visitantes hacen clic en el vínculo de mensaje de correo electrónico que contenga el protocolo [!DNL imap://] o [!DNL mail://] y que llegue a su sitio. Por ejemplo, todas las visitas procedentes de [!DNL https://mail.yahoo.com] no se cuentan como referente de correo electrónico, porque el protocolo es [!DNL https://]. Los mensajes de correo electrónico de Outlook se registran en la línea de direcciones escritas o marcadores, mientras que todos los referentes con protocolo HTTP cuyo dominio es un motor de búsqueda conocido se registran en la línea de motores de búsqueda.

**Escritos o marcadores**: los referentes escritos o marcados se registran cuando los visitantes escriben su dirección URL directamente en el explorador o si acceden al sitio seleccionando un marcador. Los dispositivos móviles informan de un tipo de referente de *`typed/bookmarked`* si no hay ningún referente en la primera visita individual de la visita.

**[!UICONTROL Dentro de su sitio]**: estos artículos son direcciones URL que son etiquetadas por los filtros de URL internos. No se contabilizan como *`referrer instances`* pero se pueden ver en los informes de otras métricas.

## Tipos de referente por interfaz {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics de marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Análisis específico </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tipos de referentes de informes </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Otros sitios web </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Motores de búsqueda </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Escritos o marcadores </li> 
    </ul> <p> Este informe solo muestra dos métricas predefinidas: instancias y visitantes únicos. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Otros sitios web </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Motores de búsqueda </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Escritos o marcadores </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Otros sitios web </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Motores de búsqueda </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Escritos o marcadores </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> Dentro del sitio web </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Notas {#section_B83A3571D64E4E7792712FAF740D7955}

* El referente, tipo de referente y dominio de referencia se establecen en la primera vista de la visita, o durante una visita cuando el referente es externo (por ejemplo, si un visitante sale del sitio, usa un motor de búsqueda y vuelve al sitio antes de que caduque la primera visita). Estos valores se establecen de forma simultánea y persisten durante toda la visita.
* No todos los tipos de referentes se enumeran en este informe. Esto quiere decir que las visitas de todo el sitio no coincidirán con las visitas en este informe.

## Historial de informes  {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Fecha | Cambiar |
|---|---|
| 16/1/2014 | El almacén de datos se ha actualizado para que coincida con la lógica usada por los Reports &amp; Analytics de marketing. Antes de esta fecha, el tipo de referente no persistía durante la visita. |

