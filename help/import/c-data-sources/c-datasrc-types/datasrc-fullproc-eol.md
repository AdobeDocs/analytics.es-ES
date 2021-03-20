---
title: Fin de vida útil para fuentes de datos de procesamiento completo
description: Razones para finalizar la vida útil y comparaciones entre la API de inserción de datos en lote y las fuentes de datos de procesamiento completo.
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 13%

---


# Fin de vida útil para fuentes de datos de procesamiento completo

Durante varios años, las fuentes de datos de procesamiento completo han permitido enviar datos de nivel de visita a Adobe Analytics. Estos datos se procesaron del mismo modo que los datos recopilados mediante nuestras bibliotecas JavaScript y el SDK de la aplicación móvil. En 2020, Adobe lanzó la [API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), que realiza las mismas funciones que las fuentes de datos de procesamiento completo, pero con funciones adicionales. En este tema se proporcionan detalles sobre la funcionalidad adicional proporcionada por la API de inserción de datos en lote y se describen las diferencias en los formatos de archivo.

A partir del 25 de marzo de 2021, Adobe impedirá que se creen nuevas conexiones de fuentes de datos de procesamiento completo. Las conexiones existentes seguirán siendo compatibles hasta que el servicio quede totalmente obsoleto. La desaprobación se producirá en 2021, aunque aún no se ha determinado una fecha específica.

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

| BDIA, FPDS, ambos | Variable BDIA | Variable de columna de procesamiento completo | Descripción |
| --- | --- | --- | --- |
| DIA | aamlh | No admitido | Sugerencia de ubicación de Adobe Audience Manager. Consulte los valores de ID válidos en la tabla de lista de la región de AAM que aparece a continuación. |
| Ambos | browserHeight | browserHeight | Altura de la ventana del navegador, en píxeles (por ejemplo, 768) |
| Ambos | browserWidth | browserWidth | Ancho de la ventana del navegador, en píxeles (por ejemplo, 1024) |
| Ambos | campaign | campaign | Código de seguimiento de la campaña de conversión |
| Ambos | canal | canal | Cadena correspondiente al canal (por ejemplo, Sección de deportes) |
| Ambos | colorDepth | colorDepth | Profundidad de color del monitor en bits (por ejemplo, 24) |
| Ambos | connectionType | connectionType | Tipo de conexión del visitante (LAN o módem) |
| DIA | contextData.key | No admitido | Los pares clave-valor se especifican en al nombrar el encabezado &quot;contextData.product&quot; o &quot;contextData.color&quot; |
| Ambos | cookiesEnabled | cookiesEnabled | `Y` o  `N` para si el visitante admite cookies de sesión de origen |
| Ambos | currencyCode | currencyCode | Código de la moneda en que están expresados los ingresos (por ejemplo, `USD`) |
| DIA | customerID.[customerIDType].authState | No admitido | Estado autenticado del visitante. Los valores admitidos son: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT o &#39;&#39; (sin distinción de mayúsculas y minúsculas). Dos comillas simples consecutivas (&#39;&#39;) hacen que el valor se omita de la cadena de consulta, lo que significa 0 cuando se efectúa la visita. Tenga en cuenta que los valores numéricos authState admitidos indican lo siguiente: 0 = DESCONOCIDO, 1 = AUTENTICADO, 2 = LOGGED_OUT. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
| DIA | customerID.[customerIDType].id | No admitido | El ID de cliente que se va a usar. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
| DIA | customerID.[customerIDType].isMCSeed | No admitido | Indica si este es o no el origen del ID de visitante de Marketing Cloud. Los valores admitidos son: 0, 1, TRUE, FALSE, &#39;&#39; (sin distinción de mayúsculas y minúsculas). El uso de 0, FALSE o dos comillas simples consecutivas (&#39;&#39;) hace que el valor se omita de la cadena de consulta. customerIDType puede ser cualquier cadena alfanumérica, pero debe considerarse que distingue entre mayúsculas y minúsculas. |
