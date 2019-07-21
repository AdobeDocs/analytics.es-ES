---
description: Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.
seo-description: Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.
seo-title: Referencia de código y datos del reenvío del lado del servidor
title: Referencia de código y datos del reenvío del lado del servidor
uuid: 3 eb 3 ea 0 f-a 530-448 d-bba 5-6408 b 2490 dc 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referencia de código y datos del reenvío del lado del servidor

Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.

## Variables de configuración {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). Consulte también [Atributos admitidos para llamadas a la API DCS](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Parámetro | Descripción |
|--- |--- |
| d_rs | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| d_dst_filter | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
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

Parameters prefixed with `c_` identify customer-defined variables. Consulte también [Atributos admitidos para llamadas a la API DCS](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Señal | Descripción |
|--- |--- |
| c_browserWidth y c_browserHeight | Anchura y altura de la ventana del navegador. |
| c_campaign | La establece s.campaign . |
| c_channel | La establece s.channel . |
| c_clientDateTime | Marca de tiempo con el formato dd/mm/aaa: mm: ss W TZ. TZ se expresa en minutos y coincide con el resultado del método Date.getTimezoneOffset. |
| c_colorDepth | Se especifica como color de 16 o 32 bits. |
| c_connectionType | Especifica el tipo de conexión. Las opciones incluyen:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Ejemplos:<ul><li>Appmeasurement: s. contextdata</li><li>[" category "] =" news ";</li><li>Signal: c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Especifica si las cookies pueden habilitarse. Las opciones incluyen: yes, no, unknown |
| c_currencyCode | Tipo de divisa usada para la transacción. |
| c_evar# | eVars personalizadas |
| c_events | La establece s.events . |
| c_hier# | Variables de jerarquía personalizada. |
| c_javaEnabled | Especifica si Java puede habilitarse. Las opciones incluyen: yes, no, unknown |
| c_javaScriptVersion | Versión de JavaScript admitida por un navegador. |
| c_latitude | Latitud numérica |
| c_linkClick | Las opciones incluyen: personalizado, salir de descarga |
| c_linkCustomName | El nombre personalizado (de haberlo) que el vínculo proporciona. |
| c_linkDownloadURL | La dirección URL de los vínculos de descarga. |
| c_linkExitURL | La dirección URL del vínculo de salida. |
| c_list# | Variables de lista personalizadas. |
| c_longitude | Longitud numérica. |
| c_mediaPlayerType | Para solicitudes de seguimiento de retransmisión de medios. Las opciones incluyen:  other, primetime |
| c_pageName | El nombre de la página (si está establecido). |
| c_pageURL | La dirección de la página en la barra de dirección del navegador. |
| c_products | La cadena de producto (la establece s.products ). |
| c_prop | Props personalizados. |
| c_purchaseID | Un ID exclusivo para la compra. |
| c_referrer | La página anterior a la página actual. |
| c_screenResolution | Anchura y altura de pantalla (en píxeles). |
| c_server | Nombre del servidor web (lo establece s.server ). |
| c_state | Región geográfica (la establece s.state ). |
| c_timezone | Diferencia horaria (en horas). |
| c_transactionID | Un ID exclusivo para una transacción. |
| c_zip | Código postal (lo establece s.zip ). |
