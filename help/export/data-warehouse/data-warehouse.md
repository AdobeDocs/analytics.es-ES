---
description: El almacén de datos hace referencia a la copia de datos de Analytics para informes personalizados y de almacenamiento, que se puede ejecutar filtrando los datos. Puede solicitar informes para mostrar las relaciones de datos avanzadas de los datos sin procesar según sus propias preguntas. Los informes del almacén de datos se envían por correo electrónico o FTP y pueden tardar hasta 72 horas en procesarse. El tiempo de procesamiento depende de la complejidad de la consulta y de la cantidad de datos solicitados.
title: Resumen de Data Warehouse
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen de Data Warehouse

El almacén de datos hace referencia a la copia de datos de Analytics para informes personalizados y de almacenamiento, que se puede ejecutar filtrando los datos. Puede solicitar informes para mostrar las relaciones de datos avanzadas de los datos sin procesar según sus propias preguntas. Los informes del almacén de datos se envían por correo electrónico o FTP y pueden tardar hasta 72 horas en procesarse. El tiempo de procesamiento depende de la complejidad de la consulta y de la cantidad de datos solicitados.

Adobe habilita el almacén de datos solo para usuarios de nivel de administrador, para grupos de informes específicos. (Puede habilitarse para grupos de informes globales y secundarios, pero no para grupos de informes resumidos). El administrador puede crear un grupo que tenga acceso al almacén de datos y, a continuación, asociar a ese grupo a usuarios que no tengan nivel de administrador.

El almacén de datos comprime automáticamente cualquier archivo que supere los 1 MB de tamaño. El tamaño máximo de datos adjuntos de correo electrónico es de 10 MB.

El almacén de datos puede procesar un número ilimitado de filas en una sola solicitud para informes programados y descargados individuales.

>[!NOTE] Data Warehouse informa del primer valor que se encuentra en el período de informe.

>[!IMPORTANT]
>
>Mediante la segmentación en valores clasificados, Analysis Workspace y Data Warehouse tratan los valores “no especificados” de forma diferente. “No especificado” en Workspace se refiere a valores que no están clasificados, mientras que “No especificado” en Data Warehouse se refiere a valores que clasificó como “No especificado”.

## Descripciones de las solicitudes del Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

En esta tabla se describen los campos y las opciones de la [!UICONTROL Data Warehouse Request] ficha.

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
    </ul> <p>El sistema de informes del almacén de datos en los grupos de informes virtuales admite el huso horario alternativo configurado en el grupo de informes virtuales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Segmentos disponibles</span> </td> 
   <td colname="col2"> <p>Permite seleccionar la parte de la población de visitantes que desea examinar y generar segmentos complejos. Puede cargar segmentos preconfigurados, crear nuevos segmentos y almacenar componentes de segmentos en una biblioteca para utilizarlos en la creación de segmentos adicionales. </p> <p>Ahora puede apilar segmentos. Al seleccionar varios segmentos, el área de previsualización, el Administrador de solicitudes y la ventana emergente Detalle de la solicitud muestran una lista de nombres separada por comas (por ejemplo, Segment1, Segment2). </p> <p>Si desea obtener más información, consulte la <a href="/help/components/c-segmentation/seg-home.md">Guía de segmentación de </a>. </p> <p>Nota: No se pueden incluir simultáneamente un filtro y un desglose en el mismo segmento, en el mismo informe del Data Warehouse. Al hacerlo, se producirá un error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Desgloses</span> </td> 
   <td colname="col2"> <p>Permite categorizar los datos mediante desgloses. Los segmentos y desgloses difieren en que un segmento filtros datos de un conjunto de datos, mientras que un desglose divide los datos en compartimentos en todos los valores válidos para el desglose. </p> También puede desglosar un informe en uno o más segmentos. Sin embargo, no puede incluir un filtro de segmento y un desglose en el mismo segmento, en el mismo informe del almacén de datos. Al hacerlo, se producirá un error. <p> Por ejemplo, utilice segmentos para eliminar un sexo del conjunto de datos y un desglose para ver los datos separados por sexo. </p> <p>Cuando se envía una solicitud del almacén de datos con varias dimensiones de varios valores (por ejemplo, varios informes de dispositivos móviles), se puede generar un número exponencial de filas a partir de una sola visita. El número de filas que se pueden generar a partir de una sola visita tiene un límite de 100 (anteriormente 1000). </p> </td> 
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
   <td colname="col2"> <p>Permite programar solicitudes de envío automático a intervalos seleccionados o como un informe único. Si utiliza el formato predeterminado, el informe llega en un mensaje de correo electrónico como archivo .csv. </p> <p>Para agregar el intervalo de fecha, debe incluirse <span class="filepath">%R</span> en el nombre de archivo. Este valor representa los valores de fecha solicitados en el informe. Por ejemplo, si se solicitan los datos del 1 al 7 de mayo de 2013, <span class="filepath">%R</span> muestra un nombre de archivo que incluye el intervalo de fecha 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

