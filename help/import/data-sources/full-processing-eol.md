---
title: Fin de vida útil para fuentes de datos de procesamiento completo
description: Obtenga más información sobre el anuncio de fin de vida útil para fuentes de datos de procesamiento completo.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 16%

---

# Fin de vida útil para fuentes de datos de procesamiento completo

Las fuentes de datos de procesamiento completo históricamente han permitido a las organizaciones enviar datos de nivel de visita a Adobe Analytics. Estos datos se procesaron del mismo modo que los datos recopilados mediante medios tradicionales de recopilación de datos, como AppMeasurement. En 2020, el Adobe lanzó el [API de inserción de datos en lote](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que realiza las mismas funciones que las fuentes de datos de procesamiento completo, pero con funciones adicionales. Esta página proporciona detalles sobre la funcionalidad adicional proporcionada por la API de inserción de datos en lote y describe las diferencias en los formatos de archivo.

El 25 de marzo de 2021, Adobe impidió que se crearan nuevas conexiones de fuentes de datos de procesamiento completo. El 31 de enero de 2022, se desactivaron todos los servicios de datos de procesamiento completo.

## Diferencias clave entre las fuentes de datos de procesamiento completo y la API de inserción de datos en lote

* La inserción masiva de datos permite enviar varios archivos para su procesamiento en paralelo. Los grupos de visitantes garantizan la continuidad del visitante y la atribución de eVar.
* La inserción masiva de datos tiene capacidades de validación de datos y gestión de errores, lo que elimina parte del trabajo administrativo del envío de datos de visitas.
* La inserción masiva de datos admite varios métodos de identificación de ID de visitantes.
* La inserción masiva de datos tiene algunos campos obligatorios adicionales: Una columna de identificación del visitante, un `pageName` (o equivalente de vínculo), `reportSuiteID`, `timestamp`y `userAgent`.
* Para garantizar la continuidad y la atribución del visitante, la inserción masiva de datos requiere que las filas de los archivos se ordenen en orden cronológico. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para obtener más información sobre el orden de la actividad del visitante en todos los archivos.
* La inserción masiva de datos requiere que los archivos estén comprimidos en .csv en formato .gzip.
* BDIA utiliza `timestamp` en lugar de `date`.

## Comparación de variables entre BDIA y fuentes de datos de procesamiento completo

Se introdujeron las siguientes variables en la inserción de datos en lote, que antes no estaban disponibles en las fuentes de datos de procesamiento completo:

* **`aamlh`**: Sugerencia de ubicación de Adobe Audience Manager.
* **`contextData.key`**: [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: variables del servicio de ID de Experience Cloud. Incluye `id`, `authState`y `isMCSeed`.
* **`hints`**: [Sugerencia del cliente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=es) variables. Incluye `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`y `wow64`.
* **`ipaddress`**: La dirección IP del visitante.
* **`language`**: La variable [Idioma](/help/components/dimensions/language.md) dimensión.
* **`list1`** - **`list3`**: [Variables de lista](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: El Experience Cloud ID del visitante.
* **`tnta`**: Carga útil de datos de Target que se utiliza en [Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=es) integraciones.
* **`trackingServer`**: La variable.[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)
* **`transactionID`**: La variable.[`transactionID`](/help/implement/vars/page-vars/transactionid.md)
* **`userAgent`**: La cadena del agente de usuario del dispositivo.

Las siguientes variables no son compatibles con la inserción masiva de datos:

* **`charSet`**: La variable. [`charSet`](/help/implement/vars/config-vars/charset.md) La inserción masiva de datos solo admite UTF-8.
* **`timezone`**: La diferencia entre la zona horaria del visitante y GMT, en horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Variables utilizadas en la recopilación de datos del Activity Map.
