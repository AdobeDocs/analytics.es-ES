---
description: El Data Warehouse hace referencia a la copia de datos de Analytics para almacenarlos y elaborar informes personalizados, que se pueden ejecutar filtrando los datos. Puede solicitar informes para mostrar las relaciones de datos avanzadas que hay entre los datos sin procesar en función de sus propias preguntas. Los informes del almacén de datos se envían por correo electrónico o mediante FTP y pueden tardar hasta 72 horas en procesarse. El tiempo de procesamiento dependerá de la complejidad de la consulta y de la cantidad de datos solicitados.
title: Resumen de Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 100%

---

# Resumen de Data Warehouse

El Data Warehouse hace referencia a la copia de datos de Analytics para almacenarlos y elaborar informes personalizados, que se pueden ejecutar filtrando los datos. Puede solicitar informes para mostrar las relaciones de datos avanzadas que hay entre los datos sin procesar en función de sus propias preguntas. Los informes del almacén de datos se envían por correo electrónico o mediante FTP y pueden tardar hasta 72 horas en procesarse. El tiempo de procesamiento dependerá de la complejidad de la consulta y de la cantidad de datos solicitados.

Adobe permite el Data Warehouse para los usuarios de nivel de administrador para grupos de informes específicos. (Se puede activar para los grupos de informes globales y secundarios, pero no para los resumidos). El administrador puede crear un grupo que tenga acceso al Data Warehouse y, luego, asociar a los usuarios que no tengan nivel de administrador a dicho grupo.

El Data Warehouse comprime automáticamente cualquier archivo que supere 1 MB de tamaño. El tamaño de adjunto de correo electrónico máximo es 10 MB.

El Data Warehouse pude procesar un número ilimitado de filas en una única solicitud para informes programados y descargados individuales.

>[!NOTE]
>
>Data Warehouse informa del primer valor que se encuentra en el período de informe.

>[!IMPORTANT]
>
>Mediante la segmentación en valores clasificados, Analysis Workspace y Data Warehouse tratan los valores “no especificados” de forma diferente. “No especificado” en Workspace se refiere a valores que no están clasificados, mientras que “No especificado” en Data Warehouse se refiere a valores que clasificó como “No especificado”.

## Descripciones de las solicitudes del Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

En esta tabla se describen los campos y las opciones de la ficha [!UICONTROL Solicitud del Data Warehouse].

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nombre de la solicitud</span> </td> 
   <td colname="col2"> Identifica la solicitud. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fecha de informes</span> </td> 
   <td colname="col2"> <p>La fecha y granularidad de la solicitud. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizado</span>: Un intervalo de fecha que puede configurarse en el calendario. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Ajuste preestablecido</span>: Un intervalo preestablecido. El intervalo preestablecido se refiere a la fecha del informe. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularidad</span>: La granularidad de la hora. Los valores válidos son Ninguno, Hora, Día, Semana, Mes, Trimestre y Año. </li> 
    </ul> <p>Los informes del Data Warehouse en los grupos de informes virtuales permiten que haya configurada una zona horaria alternativa en el grupo de informes virtuales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segmentos disponibles</span> </td> 
   <td colname="col2"> <p>Permite seleccionar la parte de la población de visitantes que debe examinarse y generar segmentos complejos. Puede cargar segmentos preconfigurados, crear nuevos segmentos y almacenar componentes de segmentos en una biblioteca para utilizarlos al crear segmentos adicionales. </p> <p>Ahora puede apilar segmentos. Cuando se seleccionan varios segmentos, el área de vista previa, el administrador de solicitudes y el mensaje emergente de los detalles de la solicitud muestran una lista de nombres separados por comas (por ejemplo, Segment1, Segment2). </p> <p>Si desea obtener más información, consulte la <a href="/help/components/segmentation/seg-home.md">Guía de segmentación de </a>. </p> <p>Nota: No se pueden incluir simultáneamente un filtro y un desglose en el mismo segmento, en el mismo informe del Data Warehouse. Al hacerlo, se producirá un error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Desgloses</span> </td> 
   <td colname="col2"> <p>Permite aplicar categorías a los datos a través de desgloses. Los segmentos se diferencian de los desgloses en que el filtro de segmento los datos fuera del conjunto de datos, mientras que el desglose divide los datos en módulos a lo largo de todos los valores válidos para dicho desglose. </p> También puede desglosar un informe en uno o varios segmentos. Sin embargo, no se pueden incluir simultáneamente un filtro y un desglose en el mismo segmento, en el mismo informe del Data Warehouse. Al hacerlo, se producirá un error. <p> Por ejemplo, los segmentos pueden utilizarse para eliminar el sexo de un conjunto de datos y los desgloses para ver los datos separados por sexo. </p> <p>Cuando se envía una solicitud del Data Warehouse con varias dimensiones multivalor (por ejemplo, varios informes de dispositivos portátiles), se puede generar un número exponencial de filas a partir de una sola visita. El número de filas que pueden estar en el resultado de una sola visita se limita a 100 (anteriormente eran 1000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Métricas</span> </td> 
   <td colname="col2">Le permite agregar métricas de las que desee informar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Orden de las métricas</span> </td> 
   <td colname="col2">Proporciona informes de desgloses clasificados, ordenados por un valor de métrica descendente, parecido a lo que se muestra en la interfaz de usuario de Reports &amp; Analytics, Data Workbench, etc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Más...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Programar envío</span> </td> 
   <td colname="col2"> <p>Permite programar solicitudes para su envío automático a intervalos seleccionados, o como un informe de envío único. Si utiliza el formato predeterminado, el informe se envía en un mensaje de correo electrónico como archivo .csv. </p> <p>Para agregar el intervalo de fecha, debe incluirse <span class="filepath">%R</span> en el nombre de archivo. Este valor representa los valores de fecha solicitados en el informe. Por ejemplo, si se solicitan los datos del 1 al 7 de mayo de 2013, <span class="filepath">%R</span> muestra un nombre de archivo que incluye el intervalo de fecha 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>
