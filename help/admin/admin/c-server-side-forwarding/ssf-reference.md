---
description: Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.
title: Referencia de datos y código del reenvío del lado del servidor
uuid: 3eb3ea0f-a530-448d-bba5-6408b2490dc8
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 95%

---

# Referencia de datos y código del reenvío del lado del servidor

Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.

## Variables de configuración {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Los parámetros prefijados con `d_*` identifican pares clave-valor especiales del sistema que emplean nuestros [servidores de recopilación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html) (DCS). Consulte también [Atributos admitidos para llamadas a la API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Parámetro | Descripción |
|--- |--- |
| d_rs | (Se establece con reenvío del lado del servidor heredado/basado en el servidor de seguimiento) <br>Se establece en los grupos de informes pasados con la visita a Analytics. |
| d_dst_filter | (Se establece con el reenvío del lado del servidor basado en grupos de informes) <br>Se establece en los ID de grupo de informes pasados con la visita a Analytics. |
| d_dst | Se establece en d_dst=1<br> si la solicitud a Analytics espera contenido acerca del destino a devolver al cliente. |
| d_mid | Experience Cloud ID transferido a Analytics. |

## Encabezados HTTP {#section_0549705E76004F9585224AEF872066C0}

Estos encabezados son campos que contienen información como solicitudes de datos y respuestas a una llamada HTTP.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| Encabezado HTTP | Descripción |
|--- |--- |
| Host | Se establece en el nombre de host de recopilación de datos del cliente, especificado en el archivo de configuración del host de Analytics. Aparece como   `host name .demdex.net` .  Consulte Explicación de las llamadas al dominio Demdex . |
| User-Agent | Se establece en el encabezado User-Agent que se pasa a Analytics. |
| X-Original-User-Agent | Solo se establece si alguno de los siguientes encabezados especificó un agente de usuario alternativo: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | Se establece en la dirección IP del cliente solicitante. Analytics ya habrá analizado el encabezado `X-Forwarded-For` entrante y determinado la dirección IP correcta que se debe usar. |
| Accept-Language | Se establece en el encabezado `Accept-Language` que se pasa a Analytics. |
| Referer | Se establece en la URL de página que se pasa a Analytics o se obtiene del encabezado Referer que se pasa a Analytics. |

## Señales definidas por el cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Los parámetros prefijados con `c_` identifican variables definidas por el cliente. Consulte también [Atributos admitidos para llamadas a la API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Señal | Descripción |
|--- |--- |
| c_browserWidth y c_browserHeight | Anchura y altura de la ventana del navegador. |
| c_campaign | La establece s.campaign . |
| c_channel | La establece s.channel . |
| c_clientDateTime | Marca de tiempo con formato   dd/mm/aaa hh:mm:ss  W TZ .    TZ se expresa en minutos y coincide con el resultado del método Date.getTimezoneOffset. |
| c_colorDepth | Se especifica como color de 16 o 32 bits. |
| c_connectionType | Especifica el tipo de conexión. Las opciones incluyen:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Ejemplos:<ul><li>AppMeasurement: s.contextData</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Signal: c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Especifica si las cookies pueden habilitarse. Las opciones incluyen: sí, no, desconocido |
| c_currencyCode | Tipo de divisa usada para la transacción. |
| c_evar# | eVars personalizadas |
| c_events | La establece s.events . |
| c_hier# | Variables de jerarquía personalizada. |
| c_javaEnabled | Especifica si Java puede habilitarse. Las opciones incluyen: sí, no, desconocido |
| c_javaScriptVersion | Versión de JavaScript admitida por un navegador. |
| c_latitude | Latitud numérica |
| c_linkClick | Las opciones incluyen: personalizado, salir de la descarga |
| c_linkCustomName | El nombre personalizado (de haberlo) que el vínculo proporciona. |
| c_linkDownloadURL | La dirección URL de los vínculos de descarga. |
| c_linkExitURL | La dirección URL del vínculo de salida. |
| c_list# | Variables de lista personalizadas. |
| c_longitude | Longitud numérica. |
| c_mediaPlayerType | Para solicitudes de seguimiento de retransmisión de medios. Las opciones incluyen: otro, primetime |
| c_pageName | El nombre de la página (si está establecido). |
| c_pageURL | La dirección de la página en la barra de dirección del navegador. |
| c_products | La cadena de producto (la establece s.products ). |
| c_prop | Props personalizados. |
| c_purchaseID | Un ID único para la compra. |
| c_referrer | La página anterior a la página actual. |
| c_screenResolution | Anchura y altura de pantalla (en píxeles). |
| c_server | Nombre del servidor web (lo establece s.server ). |
| c_state | Región geográfica (la establece s.state ). |
| c_timezone | Diferencia horaria (en horas). |
| c_transactionID | Un ID único para una transacción. |
| c_zip | Código postal (lo establece s.zip ). |
