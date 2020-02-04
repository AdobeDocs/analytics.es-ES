---
description: Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificar visitantes únicos
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Identificar visitantes únicos

Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.

## Orden de ID de visitante de Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics proporciona varios mecanismos para identificar a los visitantes. En la siguiente tabla se muestran las diferentes maneras de identificar a un visitante en Analytics (en orden de preferencia):

| Orden utilizado | Parámetro de consulta (método de recopilación) | Presente si |
|---|---|---|
| 1 | vid (s.visitorID) | Se establece s.visitorID. |
| 2 | aid (cookie s_vi) | El visitante tenía una cookie s_vi existente antes de que usted implementara el servicio de ID del visitante o ha configurado un periodo de gracia del ID del visitante. |
| 3 | mid (cookie AMCV_ establecida por el servicio de ID de visitante de Experience Cloud) | El explorador del visitante acepta cookies (de origen). |
| 4 | fid (cookie de reserva) | El explorador del visitante acepta cookies (de origen). |
| 5 | Dirección IP, agente de usuario y dirección IP de puerta de enlace | El explorador del visitante no acepta cookies. |

En muchas situaciones, podría ver 2 o 3 ID diferentes en una llamada, pero Analytics utilizará la primera ID presente de la tabla anterior como ID de visitante oficial. Por ejemplo, si está configurando una ID de visitante personalizada (incluida en el parámetro de consulta &quot;vid&quot;), esa ID se utilizará antes de que otras ID pudieran estar presentes en esa misma visita.

> [!NOTE] Cada ID de visitante de Analytics está asociado con un perfil del visitante en los servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.

## ID de visitante personalizado

Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.

La ID de visitante personalizada se puede usar en los sitios en los que tenga un solo método para identificar a los visitantes. Puede servir de ejemplo una ID que se genera cuando un usuario inicia sesión en un sitio web con un nombre de usuario y una contraseña.

Si puede derivar y administrar las [!UICONTROL ID de visitantes] de sus usuarios, puede usar los métodos siguientes para configurar la ID:

| Método | Descripción |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) | Si se usa JavaScript en el explorador, o si está usando cualquier otra biblioteca de AppMeasurement, puede configurar la ID del visitante en una variable de recopilación de datos. |
| Parámetro de cadena de consulta en la solicitud de imagen | Con este método puede pasar la [!UICONTROL ID de visitante] a Adobe mediante el parámetro de [!UICONTROL cadena de consulta vid] en una solicitud de imagen codificada. |
| API de inserción de datos | En dispositivos que usan protocolos inalámbricos que no aceptan JavaScript, puede enviar una publicación XML que contenga el elemento XML `<visitorid/>` a servidores de recopilación de Adobe desde sus servidores. |
| Reescritura de direcciones URL y VISTA | Algunas arquitecturas de implementación permiten la reescritura de direcciones URL para mantener el estado de la sesión cuando no se puede configurar una cookie. En estos casos, los servicios de ingeniería de Adobe pueden implementar una regla [!DNL VISTA] para buscar el valor de sesión en la dirección URL de la página y, después, darle formato y colocarla en los valores [!UICONTROL visid]. |
>[!CAUTION]
>**Los ID de visitante personalizados deben ser suficientemente granulares y únicos **: Una implementación no válida de los ID de visitante personalizados puede provocar que los datos sean incorrectos y que el rendimiento de los informes sea deficiente. Si el ID de visitante personalizado no es lo suficientemente único o granular, o si se establece incorrectamente en un valor predeterminado común como la cadena “NULL” o “0”, Adobe Analytics verá las visitas de muchos visitantes diferentes como un solo visitante. Esta situación da como resultado datos incorrectos, con recuentos de visitantes demasiado bajos y segmentos que no funcionan correctamente para ese visitante. Un ID de visitante personalizado insuficientemente granular también evita que los datos se propaguen correctamente entre los nodos del clúster de informes de Analytics. En este caso, un nodo se sobrecarga y no puede procesar las solicitudes de informes de manera oportuna. Finalmente, todos los informes del grupo de informes fallarán.<br>Es posible que los ID de visitante personalizados mal implementados no afecten inmediatamente al rendimiento de los informes, ya que Analytics puede con frecuencia gestionar datos desequilibrados durante varios meses. Sin embargo, con el tiempo un valor de ID de visitante personalizado mal implementado puede resultar problemático, ya que requiere que Analytics deshabilite el procesamiento de los grupos de informes afectados.</br><br>Los implementadores deben seguir la guía de que un solo valor de ID de visitante personalizado nunca debe recibir crédito por más del 1% del tráfico del grupo de informes. Aunque la guía del 1% es suficiente para la mayoría de los grupos de informes, el límite real que podría afectar al rendimiento de los informes podría ser inferior al 1% para los grupos de informes más grandes.</br>

## ID de visitante de Analytics

Cuando un usuario visita el sitio, el servidor web de Adobe configura una cookie persistente incluyéndola en la respuesta HTTP al explorador. Esta cookie se configura en el dominio de recopilación de datos especificado.

Cuando se envía una solicitud al servidor de recopilación de datos de Adobe, se comprueba la existencia de la cookie de ID de visitante (`s_vi`) en el encabezado. Si la cookie se encuentra en la solicitud, se usa para identificar al visitante. En caso contrario, el servidor genera una ID de visitante única, la establece como cookie en el encabezado de respuesta HTTP y la devuelve con la solicitud. La cookie se almacena en el explorador y se devuelve al servidor de recopilación de datos durante las visitas subsiguientes al sitio, lo que permite identificar al visitante en las distintas visitas.

### Cookies de terceros y registros CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Algunos exploradores, como Apple Safari, ya no almacenan cookies configuradas en el encabezado HTTP de los dominios que no coincidan con el dominio del sitio web actual (se trata de una cookie usada en un contexto de terceros o una cookie de terceros). Por ejemplo, si está en `mysite.com` y el servidor de recopilación de datos es `mysite.omtrdc.net`, el explorador puede rechazar la cookie que se devuelve en el encabezado HTTP desde `mysite.omtrdc.net`.

Para evitarlo, muchos clientes han implementado registros CNAME para sus servidores de recopilación de datos como parte de la [implementación de cookies de origen](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). Si se configura la asignación de un registro CNAME a un nombre de host en el dominio del cliente para el servidor de recopilación de datos (por ejemplo, si se asigna `metrics.mysite.com` a `mysite.omtrdc.net`), se almacenará la cookie de ID de visitante porque ahora coinciden los dominios de recopilación de datos y del sitio web. Así aumentan las probabilidades de que se almacene la cookie de ID de visitante, pero se obtiene una cierta sobrecarga porque es necesario configurar los registros CNAME y mantener los certificados SSL para los servidores de recopilación de datos.

### Cookies en dispositivos móviles {#section_7D05AE259E024F73A95C48BD1E419851}

A la hora de rastrear dispositivos móviles con cookies, el método de medición puede modificarse con ciertas opciones. Aunque la duración predeterminada de las cookies es de 5 años, puede modificarla con la variable del parámetro de consulta CL (`s.cookieLifetime`). Para establecer la ubicación de las cookies en implementaciones de cname, use la cadena de consulta CDP `s.cookieDomainPeriods`. Si no se modifica la configuración, el valor predeterminado es 2 y la ubicación predeterminada es domain.com. En las implementaciones que no usan CNAME, las cookies de ID de visitante se ubican en el dominio 207.net.

## Servicio de identidad

El servicio de ID reemplaza el mecanismo de ID de visitante de Analytics heredado y se requiere para la medición de vídeo de [!UICONTROL Heartbeat], Analytics para Target y las integraciones y los servicios principales futuros de Experience Cloud.

Consulte [Servicio de identidad](https://marketing.adobe.com/resources/help/en_US/mcvid/) para obtener documentación sobre este servicio.

## Identificación de dispositivos móviles

La mayoría de los dispositivos móviles aceptan cookies del explorador. Sin embargo, en los casos en los que los dispositivos no aceptan cookies, se usa otro método para identificar de forma única a los dispositivos inalámbricos.

Adobe ha identificado varios encabezados de ID de suscriptor HTTP que identifican de forma única a la mayoría de dispositivos móviles. Estos encabezados suelen incluir el número de teléfono del dispositivo (o una versión con hash) u otros identificadores. La mayoría de los dispositivos actuales cuentan con uno o varios encabezados que los identifican de forma exclusiva y que todos los servidores de recopilación de datos de Adobe usan de forma automática como ID de visitante.

En una solicitud de imagen habitual, un “1” en la ruta (`/b/ss/rsid/1`) hace que los servidores de Adobe devuelvan una imagen e intenten configurar una cookie de [!UICONTROL ID de visitante] persistente (`AMCV_` o `s_vi`). Sin embargo, si el dispositivo se reconoce como un dispositivo móvil basado en encabezados HTTP, se pasa un &quot;5&quot; en lugar del &quot;1&quot;, lo que indica que se debe devolver una imagen con formato wbmp, así como que se debe usar nuestra lista de encabezados inalámbricos reconocidos (y no una cookie) para identificar el dispositivo.

La tabla siguiente muestra el orden de los métodos de ID usados según el valor de tipo de imagen devuelto (&quot;1&quot; o &quot;5&quot;) en la ruta:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Orden de método de ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Valor predeterminado: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">ID de visitante personalizado </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Encabezado de ID de suscriptor </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Dirección IP-Agente de usuario-Dirección IP de puerta de enlace </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>El dispositivo se ha identificado como un dispositivo inalámbrico o se ha enviado <code> /5/</code> manualmente en la solicitud de la imagen: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID de visitante personalizado </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Encabezado de ID de suscriptor </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Dirección IP-Agente de usuario-Dirección IP de puerta de enlace </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

También puede pasar un &quot;1&quot; o un &quot;5&quot; en las solicitudes de imágenes manuales, pero asegúrese de que estos códigos sean mutuamente exclusivos; por tanto, pasar siempre un &quot;5&quot; no hará que se use una cookie cuando se admita. Puede incorporar su propio mecanismo para determinar si un dispositivo admite cookies y, en caso afirmativo, pasar &quot;1&quot; en la imagen en lugar de &quot;5&quot;. La mejora de la precisión en este caso se limita al número de dispositivos móviles que admitan cookies.

### Encabezados de ID de suscriptor {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Por lo general, el método de ID de suscriptor resulta más fiable que las cookies a la hora de identificar usuarios debido a la posible eliminación de cookies, a los problemas de aceptación de estas y a los relacionados con la administración de cookies de puerta de enlace.

Para mejorar los cambios relacionados con la identificación de visitantes, agréguese a la lista blanca del operador que usan los visitantes móviles. Para obtener acceso a la ID de visitante del operador, póngase en contacto con este para agregar el dominio a su lista blanca. Cuando se integre en esta lista, también dispondrá de acceso a los encabezados de ID de suscriptor a los que no podría acceder de ninguna otra manera.

Los encabezados de la siguiente lista se usan para identificar dispositivos inalámbricos. El algoritmo de procesamiento de encabezados se usa para:

1. Extraer la clave de encabezado HTTP (el nombre del encabezado, como &quot;X-Up-Calling-Line-ID&quot;)
1. Recortar todos los caracteres no alfabéticos (A-Z y a-z)
1. Convertir la clave del encabezado en minúsculas
1. Comparar el final de la clave con los de la tabla siguiente para encontrar una coincidencia:

| Encabezado | Tipo | Ejemplo |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID o dirección IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID o dirección IP | X-Wap-msisdn: 8032618185 |
| clientip | Dirección IP | Client-ip: 10.9.41.2 |
| wapipaddr | Dirección IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Dirección IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Dirección IP | UserIP: 70.214.81.241 |
| ipaddress | Dirección IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Dirección IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Por ejemplo, &quot;callinglineid&quot; coincidiría con &quot;X-Up-Calling-Line-ID&quot; y &quot;nokia-callinglineid&quot;. El tipo de encabezado nos indica qué esperar en el encabezado. Aquí se indica el orden de prioridad de los encabezados (si hay un encabezado &quot;callinglineid&quot; presente, se usa en lugar de &quot;subno&quot;).

Puede usar [Variables dinámicas](../implement/vars/page-vars/dynamic-variables.md) para extraer valores específicos de un encabezado.

## Métodos de ID de reserva

Si los demás métodos de ID de visitante fallan, Adobe configura una cookie de reserva o utiliza una combinación de dirección IP y agente de usuario para identificar al visitante.

### Método de identificación de visitantes de reserva {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement para JavaScript 1.x y JavaScript H.25.3 (comercializado en enero de 2013) contienen un nuevo método de identificación de visitantes de reserva para aquellos visitantes cuyo explorador bloquea la cookie configurada por los servidores de recopilación de datos de Adobe (denominada `s_vi`). Anteriormente, si no se podía configurar una cookie, los visitantes se identificaban con una combinación de la dirección IP y la cadena del agente de usuario durante la recopilación de datos.

Con esta actualización, si la cookie `s_vi` estándar no está disponible, se crea una cookie de reserva en el dominio del sitio web con una ID única generada aleatoriamente. Esta cookie, denominada `s_fid`, se configura con una caducidad de 2 años y se usa como método de identificación de reserva a partir de ahora. Este cambio debe provocar una mayor precisión en los recuentos de visitas y visitantes en aquellos casos en los que se no se puede configurar la cookie principal (`AMCV_` o `s_vi`).

El total de visitas incluye todos los visitantes identificados por la cookie `s_vi` o mediante un método de reserva.

### Dirección IP, agente de usuario y dirección IP de puerta de enlace {#section_104819D74C594ECE879144FCC5DEF4BF}

. Si no se pueden configurar las cookies `AMCV_` o `s_vi` y `s_fid`, los visitantes se identifican con una combinación de dirección IP y agente de usuario.
