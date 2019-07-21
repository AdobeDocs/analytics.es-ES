---
description: La mayoría de los dispositivos móviles aceptan cookies del explorador. Sin embargo, en los casos en los que los dispositivos no aceptan cookies, se usa otro método para identificar de forma única a los dispositivos inalámbricos.
keywords: Implementación de Analytics
seo-description: La mayoría de los dispositivos móviles aceptan cookies del explorador. Sin embargo, en los casos en los que los dispositivos no aceptan cookies, se usa otro método para identificar de forma única a los dispositivos inalámbricos.
seo-title: Identificación de dispositivos móviles
solution: Analytics
title: Identificación de dispositivos móviles
topic: Desarrollador e implementación
uuid: 22587 dd 1-cead -485 b-a 4 d 8-94 dfb 7 cd 9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Identificación de dispositivos móviles

La mayoría de los dispositivos móviles aceptan cookies del explorador. Sin embargo, en los casos en los que los dispositivos no aceptan cookies, se usa otro método para identificar de forma única a los dispositivos inalámbricos.

Adobe ha identificado varios [encabezados de ID de suscriptor](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) HTTP que identifican de forma única a la mayoría de dispositivos móviles. Estos encabezados suelen incluir el número de teléfono del dispositivo (o una versión con hash) u otros identificadores. La mayoría de los dispositivos actuales cuentan con uno o varios encabezados que los identifican de forma exclusiva y que todos los servidores de recopilación de datos de Adobe usan de forma automática como ID de visitante.

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Sin embargo, si el dispositivo se reconoce como un dispositivo móvil basado en encabezados HTTP, se pasa un "5" en lugar del "1", lo que indica que se debe devolver una imagen con formato wbmp, así como que se debe usar nuestra lista de encabezados inalámbricos reconocidos (y no una cookie) para identificar el dispositivo.

La tabla siguiente muestra el orden de los métodos de ID usados según el valor de tipo de imagen devuelto ("1" o "5") en la ruta:

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
   <td colname="col2"> <p>El dispositivo se ha identificado como un dispositivo inalámbrico o se ha enviado <code>/5/</code> manualmente en la solicitud de la imagen: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID de visitante personalizado </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Encabezado de ID de suscriptor </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Dirección IP-Agente de usuario-Dirección IP de puerta de enlace </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

También puede pasar un "1" o un "5" en las solicitudes de imágenes manuales, pero asegúrese de que estos códigos sean mutuamente exclusivos; por tanto, pasar siempre un "5" no hará que se use una cookie cuando se admita. Puede incorporar su propio mecanismo para determinar si un dispositivo admite cookies y, en caso afirmativo, pasar "1" en la imagen en lugar de "5". La mejora de la precisión en este caso se limita al número de dispositivos móviles que admitan cookies.

## Encabezados de ID de suscriptor {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Por lo general, el método de ID de suscriptor resulta más fiable que las cookies a la hora de identificar usuarios debido a la posible eliminación de cookies, a los problemas de aceptación de estas y a los relacionados con la administración de cookies de puerta de enlace.

Para mejorar los cambios relacionados con la identificación de visitantes, agréguese a la lista blanca del operador que usan los visitantes móviles. Para obtener acceso a la ID de visitante del operador, póngase en contacto con este para agregar el dominio a su lista blanca. Cuando se integre en esta lista, también dispondrá de acceso a los encabezados de ID de suscriptor a los que no podría acceder de ninguna otra manera.

Los encabezados de la siguiente lista se usan para identificar dispositivos inalámbricos. El algoritmo de procesamiento de encabezados se usa para:

1. Extraer la clave de encabezado HTTP (el nombre del encabezado, como "X-Up-Calling-Line-ID")
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

Por ejemplo, "callinglineid" coincidiría con "X-Up-Calling-Line-ID" y "nokia-callinglineid". El tipo de encabezado nos indica qué esperar en el encabezado. Aquí se indica el orden de prioridad de los encabezados (si hay un encabezado "callinglineid" presente, se usa en lugar de "subno").

Puede usar los métodos de API [Variables dinámicas](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262) para extraer valores específicos de un encabezado.
