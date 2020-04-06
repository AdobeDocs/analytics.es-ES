---
description: Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificar visitantes únicos
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Identificar visitantes únicos

Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.

## Orden de ID de visitante de Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics ofrece varios mecanismos para identificar visitantes. La siguiente tabla lista las diferentes formas en que se puede identificar un visitante en Analytics (en orden de preferencia):

| Pedido utilizado | Parámetro de Consulta (método de recopilación) | Presente cuando |
|---|---|---|
| 1 | vid (s.visitorID) | Se establece s.visitorID. |
| 2 | aid (cookie s_vi) | El visitante tenía una cookie s_vi existente antes de que usted implementara el servicio de ID del visitante o ha configurado un periodo de gracia del ID del visitante. |
| 3 | mid (cookie AMCV_ establecida por el servicio de ID de visitante de Experience Cloud) | El explorador del visitante acepta cookies (de origen). |
| 4 | fid (cookie de reserva) | El explorador del visitante acepta cookies (de origen). |
| 5 | Dirección IP, agente de usuario y dirección IP de puerta de enlace | El explorador del visitante no acepta cookies. |

En muchos casos, es posible que vea dos o tres ID diferentes en una llamada, pero Analytics utilizará el primer ID presente en la tabla anterior como ID de visitante oficial. Por ejemplo, si configura un ID de visitante personalizado (incluido en el parámetro de consulta &quot;vid&quot;), ese ID se utilizará antes que otros ID que puedan existir en la misma visita.

>[!NOTE] Cada ID de visitante de Analytics está asociado con un perfil del visitante en los servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.

## ID de visitante personalizado

Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.

Se puede utilizar una ID de Visitante personalizada en los sitios donde se disponga de una forma única de identificar visitantes. Un ejemplo de esto es un ID generado cuando un usuario inicia sesión en un sitio web con un nombre de usuario y una contraseña.

Si tiene la capacidad de derivar y administrar los datos [!UICONTROL visitor IDs] de los usuarios, puede utilizar los siguientes métodos para configurar el ID:

| Método | Descripción |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) | Si se utiliza JavaScript en el explorador o si utiliza cualquier otra biblioteca de AppMeasurement, puede establecer el ID de visitante en una variable de recopilación de datos. |
| Parámetro de cadena de Consulta en la solicitud de imagen | Esto le permite pasar [!UICONTROL visitor ID] a Adobe a través del [!UICONTROL vid query string] parámetro en una solicitud de imagen codificada. |
| API de inserción de datos | En dispositivos que usan protocolos inalámbricos que no aceptan JavaScript, puede enviar una publicación XML que contenga el elemento XML `<visitorid/>` a servidores de recopilación de Adobe desde sus servidores. |
| Reescritura de direcciones URL y VISTA | Algunas arquitecturas de implementación admiten el uso de la reescritura de direcciones URL para mantener el estado de la sesión cuando no se puede configurar una cookie. En estos casos, los servicios de ingeniería de Adobe pueden implementar una regla [!DNL VISTA] para buscar el valor de sesión en la dirección URL de la página y, después, darle formato y colocarla en los valores [!UICONTROL visid]. |
>[!CAUTION]
>**Los ID de visitante personalizados deben ser suficientemente granulares y únicos **: Una implementación no válida de los ID de visitante personalizados puede provocar que los datos sean incorrectos y que el rendimiento de los informes sea deficiente. Si el ID de visitante personalizado no es lo suficientemente único o granular, o si se establece incorrectamente en un valor predeterminado común como la cadena “NULL” o “0”, Adobe Analytics verá las visitas de muchos visitantes diferentes como un solo visitante. Esta situación da como resultado datos incorrectos, con recuentos de visitantes demasiado bajos y segmentos que no funcionan correctamente para ese visitante. Un ID de visitante personalizado insuficientemente granular también evita que los datos se propaguen correctamente entre los nodos del clúster de informes de Analytics. En este caso, un nodo se sobrecarga y no puede procesar las solicitudes de informes de manera oportuna. Finalmente, todos los informes del grupo de informes fallarán.<br>Es posible que los ID de visitante personalizados mal implementados no afecten inmediatamente al rendimiento de los informes, ya que Analytics puede con frecuencia gestionar datos desequilibrados durante varios meses. Sin embargo, con el tiempo un valor de ID de visitante personalizado mal implementado puede resultar problemático, ya que requiere que Analytics deshabilite el procesamiento de los grupos de informes afectados.</br><br>Los implementadores deben seguir la guía de que un solo valor de ID de visitante personalizado nunca debe recibir crédito por más del 1% del tráfico del grupo de informes. Aunque la guía del 1% es suficiente para la mayoría de los grupos de informes, el límite real que podría afectar al rendimiento de los informes podría ser inferior al 1% para los grupos de informes más grandes.</br>

## ID de visitante de Analytics

Cuando un usuario visita su sitio, el servidor web de Adobe establece una cookie persistente incluyéndola en la respuesta HTTP al explorador. Esta cookie se configura en el dominio de recopilación de datos especificado.

Cuando se envía una solicitud al servidor de recopilación de datos de Adobe, se comprueba la existencia de la cookie de ID de visitante (`s_vi`) en el encabezado. Si la cookie se encuentra en la solicitud, se usa para identificar al visitante. Si la cookie no está en la solicitud, el servidor genera un ID de visitante único, lo establece como una cookie en el encabezado de respuesta HTTP y lo devuelve con la solicitud. La cookie se almacena en el explorador y se devuelve al servidor de recopilación de datos durante las visitas posteriores al sitio, lo que permite identificar el visitante en todas las visitas.

### Cookies de terceros y registros CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Algunos exploradores, como Apple Safari, ya no almacenan cookies configuradas en el encabezado HTTP de los dominios que no coincidan con el dominio del sitio web actual (se trata de una cookie usada en un contexto de terceros o una cookie de terceros). Por ejemplo, si está en `mysite.com` y el servidor de recopilación de datos es `mysite.omtrdc.net`, el explorador puede rechazar la cookie que se devuelve en el encabezado HTTP desde `mysite.omtrdc.net`.

Para evitarlo, muchos clientes han implementado registros CNAME para sus servidores de recopilación de datos como parte de la [implementación de cookies de origen](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.translate.html). Si se configura la asignación de un registro CNAME a un nombre de host en el dominio del cliente para el servidor de recopilación de datos (por ejemplo, si se asigna `metrics.mysite.com` a `mysite.omtrdc.net`), se almacenará la cookie de ID de visitante porque ahora coinciden los dominios de recopilación de datos y del sitio web. Así aumentan las probabilidades de que se almacene la cookie de ID de visitante, pero se obtiene una cierta sobrecarga porque es necesario configurar los registros CNAME y mantener los certificados SSL para los servidores de recopilación de datos.

### Cookies en dispositivos móviles {#section_7D05AE259E024F73A95C48BD1E419851}

A la hora de rastrear dispositivos móviles con cookies, el método de medición puede modificarse con ciertas opciones. Aunque la duración predeterminada de las cookies es de 5 años, puede modificarla con la variable del parámetro de consulta CL (`s.cookieLifetime`). Para establecer la ubicación de las cookies en implementaciones de cname, use la cadena de consulta CDP `s.cookieDomainPeriods`. Si no se especifica ningún valor, el valor predeterminado es 2. y la ubicación predeterminada es domain.com. Para implementaciones que no utilizan CNAME, la ubicación de la cookie de ID de visitante se encuentra en el dominio 207.net.

## Servicio de identidad

El servicio de ID reemplaza el mecanismo de ID de visitante de Analytics heredado y se requiere para la medición de vídeo de [!UICONTROL Heartbeat], Analytics para Target y las integraciones y los servicios principales futuros de Experience Cloud.

Consulte [Servicio de identidad](https://marketing.adobe.com/resources/help/es_ES/mcvid/) para obtener documentación sobre este servicio.

## Identificación de dispositivos móviles

La mayoría de los dispositivos móviles aceptan cookies del explorador. Sin embargo, en los casos en que los dispositivos no aceptan cookies, se utiliza otro método para identificar de forma exclusiva los dispositivos inalámbricos.

Adobe ha identificado varios encabezados de ID de suscriptor HTTP que identifican de forma única a la mayoría de dispositivos móviles. Estos encabezados suelen incluir el número de teléfono del dispositivo (o una versión con hash del número) u otros identificadores. La mayoría de los dispositivos actuales tienen uno o varios encabezados que identifican el dispositivo de forma única, y todos los servidores de recopilación de datos de Adobe utilizan automáticamente esos encabezados en lugar de un ID de Visitante.

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Sin embargo, si el dispositivo se reconoce como un dispositivo móvil basado en los encabezados HTTP, se pasa un &#39;5&#39; en lugar del &#39;1&#39;, lo que indica que se debe devolver una imagen en formato wbmp y que nuestra lista de encabezados inalámbricos reconocidos (no una cookie) debe utilizarse para identificar el dispositivo.

La siguiente tabla lista el orden de los métodos de ID utilizados en función del valor de tipo de imagen devuelto (&#39;1&#39; o &#39;5&#39;) en la ruta:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Orden del método de ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Predeterminado: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">ID de visitante personalizado </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Encabezado de identificación del abonado </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Dirección IP-UserAgent-Dirección IP de puerta de enlace </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>El dispositivo se ha identificado como un dispositivo inalámbrico o se ha enviado <code> /5/</code> manualmente en la solicitud de la imagen: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID de visitante personalizado </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Encabezado de identificación del abonado </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Dirección IP-Agente de usuario-Dirección IP de puerta de enlace </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

También puede pasar un &#39;1&#39; o un &#39;5&#39; en las solicitudes de imagen manuales, pero tenga en cuenta que estos códigos son mutuamente excluyentes, por lo que siempre pasar &#39;5&#39; no aprovecha una cookie cuando se admite. Puede incorporar su propio mecanismo para determinar si un dispositivo admite cookies y, de ser así, pasar un &#39;1&#39; en la imagen en lugar de un &#39;5&#39;. La mejora de la precisión en esta situación se limita al número de dispositivos móviles que admiten cookies.

### Encabezados de ID de suscriptor {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

El método de ID del suscriptor es generalmente más confiable que una cookie para la identificación del usuario debido a la eliminación de cookies, problemas de aceptación de cookies y problemas de administración de cookies de puerta de enlace.

Puede mejorar los cambios en la identificación de un visitante agregándose a la lista blanca de la portadora que utilizan los visitantes móviles. Para obtener acceso al ID de visitante del portador, póngase en contacto con el portador para agregar su dominio a su lista blanca. Si se encuentra en la lista blanca de un operador, también tiene acceso a los encabezados de ID de suscriptor a los que de otro modo no podría acceder.

La siguiente lista de encabezados se utiliza para identificar dispositivos inalámbricos. El algoritmo para procesar los encabezados es

1. extraiga la clave de encabezado HTTP (el nombre del encabezado, como &quot;X-Up-Calling-Line-ID&quot;)
1. recortar todos los caracteres no alfabéticos (A-Z y a-z)
1. convertir la clave de encabezado a minúsculas
1. compare el final de la clave con los de la siguiente tabla para encontrar una coincidencia:

| Encabezado | Tipo | Ejemplo |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| reenvidedfor | ID o dirección IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID o dirección IP | X-Wap-msisdn: 8032618185 |
| clientip | Dirección IP | Client-ip: 10.9.41.2 |
| wapipaddr | Dirección IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Dirección IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Dirección IP | UserIP: 70 214 81 241 |
| ipaddress | Dirección IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Dirección IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Por ejemplo, &quot;callinglineid&quot; coincidiría con &quot;X-Up-Calling-Line-ID&quot; y &quot;nokia-callinglineid&quot;. El tipo de encabezado nos indica qué esperar en el encabezado. El orden de prioridad del encabezado se muestra aquí (si hay un encabezado &quot;callinglineid&quot; presente, se utiliza en lugar de &quot;subno&quot;).

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## Métodos de ID de reserva

Si los demás métodos de ID de visitante fallan, Adobe configura una cookie de reserva o utiliza una combinación de dirección IP y agente de usuario para identificar al visitante.

### Método de identificación de visitantes de reserva {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement para JavaScript 1.x y JavaScript H.25.3 (comercializado en enero de 2013) contienen un nuevo método de identificación de visitantes de reserva para aquellos visitantes cuyo explorador bloquea la cookie configurada por los servidores de recopilación de datos de Adobe (denominada `s_vi`). Anteriormente, si no se podía configurar una cookie, los visitantes se identificaban con una combinación de la dirección IP y la cadena del agente de usuario durante la recopilación de datos.

Con esta actualización, si la cookie `s_vi` estándar no está disponible, se crea una cookie de reserva en el dominio del sitio web con una ID única generada aleatoriamente. Esta cookie, denominada `s_fid`, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora. Este cambio debe provocar una mayor precisión en los recuentos de visitas y visitantes en aquellos casos en los que se no se puede configurar la cookie principal (`AMCV_` o `s_vi`).

El total de visitas incluye todos los visitantes identificados por la cookie `s_vi` o mediante un método de reserva.

### Dirección IP, agente de usuario y dirección IP de puerta de enlace {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si no se pueden configurar las cookies `AMCV_` o `s_vi` y `s_fid`, los visitantes se identifican con una combinación de dirección IP y agente de usuario.
