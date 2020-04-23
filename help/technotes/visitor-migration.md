---
description: La migración de visitantes es un proceso en el que las cookies de ID de visitante se migran de un dominio a otro.
keywords: Analytics Implementation
title: Migración de visitantes
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migración de visitantes

La migración de visitantes es un proceso en el que las cookies de ID de visitante se migran de un dominio a otro.

La migración de Visitantes permite conservar las cookies de identificación de visitante al cambiar los dominios de recopilación de datos. Los dominios de recopilación de datos pueden cambiar por los siguientes motivos:

* Se cambia de `2o7.net` a `omtrdc.net` ([Recopilación de datos regionales](https://marketing.adobe.com/resources/help/es_ES/whitepapers/rdc/)).

* Implementación del [Servicio de ID de visitante de Experience Cloud](https://marketing.adobe.com/resources/help/es_ES/mcvid/) y cambio de un CNAME o dominio de recopilación de datos de origen a `2o7.net` o `omtrdc.net` ([Recopilación de datos regionales](https://marketing.adobe.com/resources/help/es_ES/whitepapers/rdc/))

* Se cambia de `2o7.net` u `omtrdc.net` a un cname o un servidor de recopilación de datos de origen ([Cookies de origen)](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.translate.html).

* Cambio de un CNAME a otro (cambio de dominios).

Una vez configurada la migración de visitante, cuando un usuario visita el nuevo dominio sin una cookie de ID de visitante, el servidor redirige al nombre de host de recopilación de datos anterior, recupera las cookies de ID de visitante disponibles y, a continuación, redirige al nuevo dominio. Si no se encuentra un ID de Visitante en el nombre de host anterior, se genera un nuevo ID. Esto ocurre sólo una vez por visitante.

## Proceso de migración de visitantes {#section_FF0C5C5CAEF343FFA1892B29311F7160}

La siguiente tabla lista las tareas necesarias para la migración de visitantes:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Para comenzar:</b> Póngase en <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html"  >contacto con el Servicio de atención al cliente</a> y especifique el o los dominios que desea migrar, así como el período de migración que desea habilitar (30, 60 o 90 días). Asegúrese de incluir los dominios seguros y no seguros. </p> </td> 
   <td colname="col3"> <p>Cree una lista con la sintaxis <i>exacta</i> de los dominios a los que desea migrar y desde los que desea realizar la migración. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Los nombres de host de migración se configuran en el servidor de recopilación de datos de Adobe. El Servicio de atención al cliente le informará cuando se realice el cambio para que pueda planificar el próximo paso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Más de 6 horas después del cambio de configuración</b>: Actualice las variables <code> s.trackingServer</code> y <code> s.trackingServerSecure</code> en su código JavaScript de Analytics para utilizar los nuevos servidores de recopilación de datos. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inmediatamente después de actualizar el código</b>de Analytics: Pruebe el sitio para verificar que se esté redireccionando al dominio de recopilación de datos anterior. </p> </td> 
   <td colname="col3"> <p>Use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. Si se produce un error en alguna de estas redirecciones, póngase en contacto con el Servicio de atención al cliente inmediatamente para asegurarse de que la migración se ha configurado correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Durante todo el período</b>de migración: Mantenga activo el registro DNS del nombre de host anterior. </p> </td> 
   <td colname="col3"> <p>El nombre de host anterior debe resolverse mediante DNS o no se producirá la migración de cookies. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables visitorMigrationKey y visitorMigrationServer obsoletas {#section_32FCEE2575944D039EA0FEBFB5814259}

En marzo de 2013, las variables de recopilación de datos `visitorMigrationKey`, `visitorMigrationServer` y `visitorMigrationServerSecure` quedaron obsoletas y ya no se usan. Los datos que anteriormente contenían estas variables ahora se almacenan en servidores de Adobe para mayor seguridad.
