---
description: La migración de visitantes es un proceso en el que las cookies de ID de visitante se migran de un dominio a otro.
keywords: Analytics Implementation
solution: Analytics
title: Migración de visitantes
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Migración de visitantes

La migración de visitantes es un proceso en el que las cookies de ID de visitante se migran de un dominio a otro.

La migración de visitantes permite preservar las cookies de identificación de visitantes al cambiar de dominio de recopilación de datos. Los dominios de recopilación de datos pueden cambiar por las siguientes razones:

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* Se cambia de un CNAME a otro (cambio de dominios).

Tras configurar la migración de visitantes, si un usuario visita el nuevo dominio sin una cookie de ID de visitante, el servidor lo redirigirá al nombre de host de recopilación de datos anterior, recuperará las cookies de ID de visitante disponibles y lo volverá a redirigir al nuevo dominio. Si no se encuentra ninguna ID de visitante en el nombre de host anterior, se generará una ID nueva. Esto solo sucede una vez por visitante.

## Proceso de migración de visitantes {#section_FF0C5C5CAEF343FFA1892B29311F7160}

La tabla siguiente resume las tareas necesarias para la migración de visitantes:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Para comenzar:</b> Póngase en <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"  >contacto con el Servicio de atención al cliente</a> y especifique el o los dominios que desea migrar, así como el período de migración que desea habilitar (30, 60 o 90 días). Asegúrese de incluir los dominios seguros y no seguros. </p> </td> 
   <td colname="col3"> <p>Cree una lista con la sintaxis <i>exacta</i> de los dominios de origen y destino de la migración. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Los nombres de host de migración se encuentran configurados en el servidor de recopilación de datos de Adobe. El Servicio de atención al cliente le informará de la fecha del cambio para que pueda planear el paso siguiente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Más de 6 horas después del cambio de configuración</b>: Actualice las variables <code> s.trackingServer</code> y <code> s.trackingServerSecure</code> en su código JavaScript de Analytics para utilizar los nuevos servidores de recopilación de datos. </p> </td> 
   <td colname="col3"> <p>Después de realizar este cambio, utilice un <a href="/help/implement/impl-testing/packet-monitor.md"  >Analizador de paquetes</a> para comprobar que la solicitud de imagen de Analytics va al servidor de recopilación de datos actualizado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inmediatamente después de actualizar su código de Analytics</b>: Pruebe el sitio para comprobar que se esté redireccionando al dominio anterior de recopilación de datos. </p> </td> 
   <td colname="col3"> <p>Utilice un <a href="/help/implement/impl-testing/packet-monitor.md"  >Analizador de paquetes</a> para comprobar que al acceder al sitio por primera vez, o después de borrar las cookies, ve tres códigos de estado HTTP 302 (redirección) antes del código de estado HTTP 200 (OK). Si se producen errores durante alguna de estas redirecciones, póngase en contacto con el Servicio de atención al cliente de forma inmediata para comprobar que la migración se ha configurado correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Durante todo el período de migración</b>: Mantenga activo el registro DNS del nombre de host anterior. </p> </td> 
   <td colname="col3"> <p>El nombre de host anterior debe resolverse con un registro DNS o las cookies no se migrarán. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables visitorMigrationKey y visitorMigrationServer obsoletas {#section_32FCEE2575944D039EA0FEBFB5814259}

En marzo de 2013, las variables de recopilación de datos `visitorMigrationKey`, `visitorMigrationServer` y `visitorMigrationServerSecure` quedaron obsoletas y ya no se usan. Los datos que anteriormente contenían estas variables ahora se almacenan en servidores de Adobe para mayor seguridad.
