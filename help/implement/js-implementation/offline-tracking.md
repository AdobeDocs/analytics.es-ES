---
description: Las funciones y variables siguientes permiten almacenar llamadas de medición cuando la aplicación se encuentra sin conexión.
keywords: Implementación de Analytics
seo-description: Las funciones y variables siguientes permiten almacenar llamadas de medición cuando la aplicación se encuentra sin conexión.
seo-title: Seguimiento sin conexión
solution: Analytics
title: Seguimiento sin conexión
topic: Desarrollador e implementación
uuid: f 7 c 55 aef -28 a 4-4 f 2 f -8 f 47-792 a 05 f 9525 b
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Seguimiento sin conexión

Las funciones y variables siguientes permiten almacenar llamadas de medición cuando la aplicación se encuentra sin conexión.

>[!NOTE]
>
>Para habilitar el seguimiento sin conexión, el grupo de informes debe tener habilitada la marca de fecha y hora. Si estas marcas se encuentran habilitadas en el grupo de informes, la propiedad de configuración `trackOffline` *debe* ser verdadera. Si no están habilitadas, la propiedad `trackOffline` *debe* tener el valor false. Si esta configuración no se realiza correctamente, se perderán datos. Si no está seguro de si un grupo de informes se ha habilitado para las marcas de tiempo, [póngase en contacto con el servicio de atención al cliente](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

Cuando se habilita, AppMeasurement sin conexión se comporta de esta manera:

* La aplicación envía una llamada al servidor, pero se produce un error en la transmisión de datos.
* AppMeasurement genera una marca de fecha y hora para la visita actual.
* AppMeasurement almacena en el búfer los datos de la visita y realiza una copia de seguridad de esos datos para un almacenamiento persistente para evitar la pérdida de datos.

En cada una de las visitas posteriores o en el intervalo definido por `offlineThrottleDelay`, AppMeasurement intenta enviar los datos de la visita almacenados en el búfer, manteniendo el orden de la visita original. Si se produce un error en la transmisión de datos, continúa almacenando en el búfer los datos de la visita (continúa aunque el dispositivo esté sin conexión).

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propiedad o método </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>Valor predeterminado: false </p> <p>Habilita o deshabilita el seguimiento sin conexión para la biblioteca de medición. </p> <p> <b>Ejemplos:</b> </p> 
    <code class="syntax c">s. trackoffline = true; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>Valor predeterminado: sin límite </p> <p>Número máximo de visitas sin conexión almacenadas en la cola. </p> <p> <b>Ejemplos:</b> </p> 
    <code class="syntax c">s. offlinehitlimit = 100; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>Valor predeterminado: 0 </p> <p>Especifica una cadencia (o retraso) en milisegundos para el envío de datos de visitas almacenados en el búfer cuando AppMeasurement detecta una conexión de red activa. De esta forma se mitiga el impacto en el rendimiento cuando se envían varias visitas en la aplicación. </p> <p>Por ejemplo, si offlineThrottleDelay=1000 y se tardan 300 ms en enviar los datos de la visita, AppMeasurement esperará 700 ms antes de enviar la siguiente visita almacenada en el búfer. </p> 
    <code class="syntax c">s. offlinethrottledelay = 1000; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> Establece manualmente el estado en línea o sin conexión del objeto de medición. La biblioteca detecta automáticamente si el dispositivo está en línea o sin conexión, de modo que estos métodos solo son necesarios si quiere forzar la medición sin conexión. <code> forceOnline</code> solo se usa para volver al estado en línea después de haber pasado manualmente al estado sin conexión. </p> <p>Cuando la medición está sin conexión: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> Si <code>trackOffline</code> es verdadera: las visitas se almacenan hasta que la medición pasa a en línea. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> Si <code>trackOffline</code> es falsa: las visitas se descartan. </li> 
    </ul> <p> <b>Ejemplos:</b> </p> 
    <code class="syntax c">s. forceoffline ();

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
