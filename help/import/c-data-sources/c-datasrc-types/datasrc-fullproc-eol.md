---
title: Fin de vida útil para fuentes de datos de procesamiento completo
description: Razones para finalizar la vida útil y comparaciones entre la API de inserción de datos en lote y las fuentes de datos de procesamiento completo.
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
translation-type: tm+mt
source-git-commit: 53b15f9c5895e856ff627fbc520d4743fbc57eba
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 32%

---

# Fin de vida útil para fuentes de datos de procesamiento completo

Durante varios años, las fuentes de datos de procesamiento completo han permitido enviar datos de nivel de visita a Adobe Analytics. Estos datos se procesaron del mismo modo que los datos recopilados mediante nuestras bibliotecas JavaScript y el SDK de la aplicación móvil. En 2020, Adobe lanzó la [API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), que realiza las mismas funciones que las fuentes de datos de procesamiento completo, pero con funciones adicionales. En este tema se proporcionan detalles sobre la funcionalidad adicional proporcionada por la API de inserción de datos en lote y se describen las diferencias en los formatos de archivo.

A partir del 25 de marzo de 2021, Adobe impedirá que se creen nuevas conexiones de fuentes de datos de procesamiento completo. Las conexiones existentes seguirán siendo compatibles hasta que el servicio quede totalmente obsoleto el 31 de julio de 2021.

## ¿Por qué queremos dejar de usar esta función?

La API de inserción masiva de datos (BDIA) proporciona funcionalidad adicional y cubre todos los casos de uso admitidos por el procesamiento completo. Creemos que será mejor usar la API de inserción masiva de datos.

## Diferencias clave entre las fuentes de datos de procesamiento completo y la API de inserción de datos en lotes

* La inserción masiva de datos permite enviar varios archivos que se pueden procesar en paralelo. Puede utilizar Grupos de visitantes para garantizar la continuidad del visitante y la atribución de eVar.
* La inserción masiva de datos tiene funciones de validación de datos y de gestión de errores, lo que elimina parte del trabajo administrativo del envío de datos de visitas.
* La inserción masiva de datos admite varias opciones para los ID de visitante. Puede enviar tanto el ID de Analytics como el ID de Marketing Cloud (consulte [Servicio de identidad](https://experienceleague.adobe.com/docs/id-service/using/home.html) para obtener más información). Además, puede utilizar su propio ID como [semilla para generar un ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* La inserción masiva de datos admite variables de datos de lista y contexto.
* La inserción masiva de datos no admite datos de Activity Map.

## Diferencias clave en el formato de archivo y el contenido

* La inserción masiva de datos tiene algunos campos obligatorios adicionales. Consulte la [documentación](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para obtener más información.
* Para garantizar la continuidad y la atribución del visitante, la inserción masiva de datos requiere que las filas de los archivos se ordenen en orden cronológico. Consulte [Grupos de visitantes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) para obtener más información sobre la ordenación de la actividad de los visitantes en todos los archivos.
* La inserción masiva de datos requiere que los archivos estén comprimidos en .csv en formato .gzip.
* BDIA utiliza &quot;marca de tiempo&quot; en lugar de &quot;fecha&quot;.

Para obtener más información, consulte la siguiente comparación de los valores de campo disponibles en Inserción de datos en lote (BDIA) y Fuentes de datos de procesamiento completo (FPDS).

## Comparación de los valores de campo disponibles en BDIA y FPDS

| Variable BDIA | Variable de columna de procesamiento completo | Descripción |
| --- | --- | --- |
| aamlh | No admitido | Sugerencia de ubicación de Adobe Audience Manager. |
| browserHeight | browserHeight | Altura de la ventana del navegador, en píxeles (por ejemplo, 768) |
| browserWidth | browserWidth | Ancho de la ventana del navegador, en píxeles (por ejemplo, 1024) |
| campaign | campaign | Código de seguimiento de la campaña de conversión |
| canal | canal | Cadena correspondiente al canal (por ejemplo, Sección de deportes) |
| colorDepth | colorDepth | Profundidad de color del monitor en bits (por ejemplo, 24) |
| connectionType | connectionType | Tipo de conexión del visitante (LAN o módem) |
| contextData.key | No admitido | Los pares clave-valor se especifican en al nombrar el encabezado &quot;contextData.product&quot; o &quot;contextData.color&quot; |
| cookiesEnabled | cookiesEnabled | `Y` o  `N` para si el visitante admite cookies de sesión de origen |
| currencyCode | currencyCode | Código de la moneda en que están expresados los ingresos (por ejemplo, `USD`) |
| customerID.[customerIDType].authState | No admitido | Estado autenticado del visitante. Los valores admitidos son: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT o &#39;&#39; (sin distinción de mayúsculas y minúsculas). Dos comillas simples consecutivas (&#39;&#39;) hacen que el valor se omita de la cadena de consulta, lo que significa 0 cuando se efectúa la visita. Tenga en cuenta que los valores numéricos authState admitidos indican lo siguiente: 0 = DESCONOCIDO, 1 = AUTENTICADO, 2 = LOGGED_OUT. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
| customerID.[customerIDType].id | No admitido | El ID de cliente que se va a usar. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
| customerID.[customerIDType].isMCSeed | No admitido | Indica si este es o no el origen del ID de visitante de Marketing Cloud. Los valores admitidos son: 0, 1, TRUE, FALSE, &#39;&#39; (sin distinción de mayúsculas y minúsculas). El uso de 0, FALSE o dos comillas simples consecutivas (&#39;&#39;) hace que el valor se omita de la cadena de consulta. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
| eVarN | eVarN, es decir `<eVar2>`...`<eVar>` | Nombre de la eVar de conversión. Se pueden usar hasta 75 eVars ( eVar1 - eVar75 ) Puede especificar el nombre del eVar (eVar12) o un nombre descriptivo (Campaña publicitaria 3). |
| Events | Events | [Cadena de eventos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars), con el mismo formato que la variable s.events. Por ejemplo: scAdd,event1,event7 |
| hierN | hierN, es decir, `<hier2>`...`</hier2>` | Nombre de la jerarquía. Se pueden usar hasta cinco jerarquías ( hier1 - hier5 ). Puede especificar el nombre de jerarquía predeterminado `hier2` o un nombre descriptivo (Barcelona). |
| homePage | homePage | Y o N, según si la página actual es la página principal del visitante. |
| ipaddress | No admitido | La dirección IP del visitante. |
| javaEnabled | javaEnabled | Y o N para indicar si el visitante tiene Java habilitado. |
| javaScriptVersion | javaScriptVersion | Versión de JavaScript (por ejemplo, 1.3). |
| idioma | No admitido | El idioma admitido del explorador. Por ejemplo: `en-us`. |
| linkName | linkName | Nombre del vínculo. |
| linkType | linkType | Tipo de vínculo. Los valores admitidos son: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF del vínculo. |
| listn Por ejemplo, list2. | No admitido | Una lista delimitada de valores que se pasan a una variable y se incluyen en los informes como elementos de línea individuales |
| marketingCloudVisitorID | No admitido | Marketing Cloud ID. Consulte [Identificación de visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) y Servicio de ID de visitante de Marketing Cloud |
| No admitido | charSet | Conjunto de caracteres admitido para el sitio web. Por ejemplo: UTF-8, ISO-8859-1, etc. |
| No admitido | clickAction | Identificador de objeto correspondiente al mapa de clics del visitante (oid) |
| No admitido | clickActionType | Tipo de identificador de objeto correspondiente al mapa de clics del visitante (oidt) |
| No admitido | clickContext | Identificador de página correspondiente al mapa de clics del visitante (pid) |
| No admitido | clickContextType | Tipo de identificador de página correspondiente al mapa de clics del visitante (pidt) |
| No admitido | clickSourceID | Índice de fuentes correspondiente al mapa de clics del visitante (oi) |
| No admitido | clickTag | Nombre de etiqueta de objetos correspondiente al mapa de clics del visitante (ot) |
| No admitido | scXmlVer | Número de versión de la solicitud XML de los informes de marketing (por ejemplo, 1.0). |
| No admitido | timezone | Diferencia entre la zona horaria del visitante y GMT, en horas (por ejemplo, -8). |
| pageName | pageName | Nombre de la página |
| pageType | pageType | Tipo de página (por ejemplo, &quot;Página de error&quot;). |
| pageURL | pageURL | Dirección URL de la página (por ejemplo, https://www.example.com/index.html). |
| plugins | plugins | Lista separada por punto y coma de los nombres de los complementos del navegador. |
| products | products | Lista de todos los productos de la página. Separe los productos con una coma. Por ejemplo: Deportes;Pelota;1;5,95,Juguetes; Superior;1:1,99. |
| prop1 - prop75 | propN, es decir, `<prop2>`...`</prop2>` | Cadena de número de propiedad (por ejemplo, Sección de deportes). |
| propN | propN | Valores de las propiedades. |
| purchaseID | purchaseID | Número de ID de la compra. |
| referente | referente | Dirección URL del referente de la página. |
| reportSuiteID | s_account | Especifica los grupos de informes en los que se desea enviar datos. Debe separar varias ID de grupo de informes con una coma. |
| resolution | resolution | Resolución de pantalla (por ejemplo, 1024x768). |
| servidor | servidor | Cadena del servidor. |
| state | state | Cadena de estado de la conversión. |
| timestamp | date | Utilice el formato de fecha ISO 8601 AAAA-MM-DDThh:mm:ss±UTC_offset (por ejemplo, 2021-09-01T12:00:00-07:00 ) o el formato de tiempo Unix (el número de segundos transcurridos desde el 1 de enero de 1970). . |
| trackingServer | No admitido | Solo se puede proporcionar mediante el encabezado de columna. |
| transactionID | No admitido | Valor común que se usa para enlazar conjuntamente actividades de usuario de multicanal para los informes. Para obtener más información, consulte la [Guía del usuario de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | No admitido | Cadena del agente de usuario |
| visitorID | visitorID | ID de Analytics del visitante. Consulte [Identificación de visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| zip | zip | Código postal de la conversión. |
