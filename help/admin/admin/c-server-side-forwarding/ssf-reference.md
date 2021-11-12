---
description: Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.
title: Referencia de datos y código del reenvío del lado del servidor
uuid: 3eb3ea0f-a530-448d-bba5-6408b2490dc8
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
source-git-commit: 27af710f1ce9d85b1177fa4c5fd4d3f6e2875a48
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 92%

---

# Referencia de datos y código del reenvío del lado del servidor

Una lista exhaustiva con descripciones de las variables de configuración, los encabezados HTTP y las señales de datos en las llamadas de reenvío del lado del servidor.

## Variables de configuración {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Los parámetros prefijados con `d_*` identifican pares clave-valor especiales del sistema que emplean nuestros [servidores de recopilación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=es) (DCS). Consulte también [Atributos admitidos para llamadas a la API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=es).

| Parámetro | Descripción |
|--- |--- |
| `d_rs` | (Se establece con reenvío del lado del servidor heredado/basado en el servidor de seguimiento) <br>Se establece en los grupos de informes pasados con la visita a Analytics. |
| `d_dst_filter` | (Se establece con el reenvío del lado del servidor basado en grupos de informes) <br>Se establece en los ID de grupo de informes pasados con la visita a Analytics. |
| `d_dst` | Se establece en `d_dst=1` si la solicitud a Analytics espera contenido acerca del destino a devolver al cliente.<br> |
| `d_mid` | Experience Cloud ID transferido a Analytics. |

## Encabezados HTTP {#section_0549705E76004F9585224AEF872066C0}

Estos encabezados son campos que contienen información como solicitudes de datos y respuestas a una llamada HTTP.

| Encabezado HTTP | Descripción | h_ key aceptado por el Audience Manager |
| --- | --- | --- |
| Host | Se establece en el nombre de host de recopilación de datos del cliente, especificado en el archivo de configuración del host de Analytics. Aparece como `host name .demdex.net`. Consulte [Explicación de las llamadas al dominio Demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=es). | `h_host` |
| User-Agent | Se establece en el encabezado User-Agent que se pasa a Analytics. | `h_user-agent` |
| Accept-Language | Se establece en el encabezado `Accept-Language` que se pasa a Analytics. | `h_accept-language` |
| Referer | Se establece en la URL de página que se pasa a Analytics o se obtiene del encabezado `Referer` que se pasa a Analytics. | `h_referer` |
| Referente | Se establece en la URL de página que se pasa a Analytics o se obtiene del encabezado `Referrer` que se pasa a Analytics. | `h_referrer` |
| Fecha | Se establece en el encabezado `Date` que se pasa a Analytics. | `h_date` |

Además, una `h_ip` se genera a partir de la IP del host que envía la solicitud al DCS.

## Señales definidas por el cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Los parámetros prefijados con `c_` identifican variables definidas por el cliente. Consulte también [Atributos admitidos para llamadas a la API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Señal | Descripción |
| --- |--- |
| `c_browserWidth`  y `c_browserHeight` | Anchura y altura de la ventana del navegador. |
| `c_campaign` | Configurar por `s.campaign`. |
| `c_channel` | Configurar por `s.channel`. |
| `c_clientDateTime` | Marca de tiempo con el formato `dd/mm/yyy hh:mm:ss  W TZ` . `TZ` se expresa en minutos y coincide con el resultado del método `Date.getTimezoneOffset` |
| `c_colorDepth` | Se especifica como color de 16 o 32 bits. |
| `c_connectionType` | Especifica el tipo de conexión. Las opciones incluyen:<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Ejemplos:<ul><li>AppMeasurement: `s.contextData`</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Señal: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Especifica si las cookies pueden habilitarse. Las opciones incluyen: sí, no, desconocido |
| `c_currencyCode` | Tipo de divisa usada para la transacción. |
| `c_evar#` | eVars personalizadas |
| `c_events` | Configurar por `s.events`. |
| `c_hier#` | Variables de jerarquía personalizada. |
| `c_javaEnabled` | Especifica si Java puede habilitarse. Las opciones incluyen: sí, no, desconocido |
| `c_javaScriptVersion` | Versión de JavaScript admitida por un navegador. |
| `c_latitude` | Latitud numérica |
| `c_linkClick` | Las opciones incluyen: personalizado, salir de la descarga |
| `c_linkCustomName` | El nombre personalizado (de haberlo) que el vínculo proporciona. |
| `c_linkDownloadURL` | La dirección URL de los vínculos de descarga. |
| `c_linkExitURL` | La dirección URL del vínculo de salida. |
| `c_list#` | Variables de lista personalizadas. |
| `c_longitude` | Longitud numérica. |
| `c_mediaPlayerType` | Para solicitudes de seguimiento de retransmisión de medios. Las opciones incluyen: otro, primetime |
| `c_pageName` | El nombre de la página (si está establecido). |
| `c_pageURL` | La dirección de la página en la barra de dirección del navegador. |
| `c_products` | La cadena de producto (la establece `s.products`). |
| `c_prop` | Props personalizados. |
| `c_purchaseID` | Un ID único para la compra. |
| `c_referrer` | La página anterior a la página actual. |
| `c_screenResolution` | Anchura y altura de pantalla (en píxeles). |
| `c_server` | Nombre del servidor web (lo establece `s.server`). |
| `c_state` | Región geográfica (establecida por `s.state`). |
| `c_timezone` | Diferencia horaria (en horas). |
| `c_transactionID` | Un ID único para una transacción. |
| `c_zip` | Código postal (configurado por `s.zip`). |
