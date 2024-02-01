---
title: Fin de la vida útil de las fuentes de datos de procesamiento completo
description: Obtenga más información sobre el anuncio de fin de vida útil para fuentes de datos de procesamiento completo.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# Fin de la vida útil de las fuentes de datos de procesamiento completo

Históricamente, las fuentes de datos de procesamiento completo han permitido a las organizaciones enviar datos de nivel de visita a Adobe Analytics. Estos datos se procesaron de la misma manera que los datos recopilados a través de medios tradicionales de recopilación de datos, como el AppMeasurement. En 2020, el Adobe publicó el [API de inserción masiva de datos](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que realiza las mismas funciones que las fuentes de datos de procesamiento completo, pero con funciones adicionales. Esta página proporciona detalles sobre la funcionalidad adicional proporcionada por la API de inserción de datos en lote y describe las diferencias en los formatos de archivo.

El 25 de marzo de 2021, el Adobe impidió que se crearan nuevas conexiones de fuentes de datos de procesamiento completo. El 31 de enero de 2022, se desactivaron todos los servicios de procesamiento completo de datos.

## Diferencias clave entre las fuentes de datos de procesamiento completo y la API de inserción de datos en lote

* La inserción de datos en lote permite enviar varios archivos para un procesamiento paralelo. Los grupos de visitantes garantizan la continuidad del visitante y la atribución de eVar.
* La inserción de datos en lote tiene funcionalidades de validación de datos y gestión de errores, lo que elimina parte del trabajo administrativo del envío de datos de visitas.
* La inserción de datos en lote admite varios métodos de identificación de ID de visitante.
* La inserción de datos en lote tiene algunos campos obligatorios adicionales: Una columna de identificación del visitante, un `pageName` (o vínculo equivalente), `reportSuiteID`, `timestamp`, y `userAgent`.
* Para garantizar la continuidad y la atribución del visitante, la inserción de datos en lote requiere que las filas de los archivos se ordenen en orden cronológico. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para obtener más información sobre el orden de la actividad del visitante en todos los archivos.
* La inserción de datos en lote requiere que los archivos estén comprimidos en .csv en formato .gzip.
* BDIA utiliza `timestamp` en lugar de `date`.

## Comparación de variables entre BDIA y fuentes de datos de procesamiento completo

Las siguientes variables se introdujeron para la inserción de datos en lote, que antes no estaba disponible en las fuentes de datos de procesamiento completo:

* **`aamlh`**: sugerencia de ubicación de Adobe Audience Manager.
* **`contextData.key`**: [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: Variables de servicio de ID de Experience Cloud. Incluye `id`, `authState`y `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variables. Incluye `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`, y `wow64`.
* **`ipaddress`**: la dirección IP del visitante.
* **`language`**: La [Idioma](/help/components/dimensions/language.md) dimensión.
* **`list1`** - **`list3`**: [Variables de lista](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: ID de Experience Cloud del visitante.
* **`tnta`**: Carga útil de datos de destino utilizada en [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=es) integraciones.
* **`trackingServer`**: La [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variable.
* **`transactionID`**: La [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable.
* **`userAgent`**: la cadena del agente de usuario del dispositivo.

Las siguientes variables no son compatibles mediante la inserción de datos en lote:

* **`charSet`**: La [`charSet`](/help/implement/vars/config-vars/charset.md) variable. La inserción de datos en lote solo admite UTF-8.
* **`timezone`**: La diferencia de zona horaria del visitante con respecto a la zona GMT, en horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: variables utilizadas en la recopilación de datos de Activity Map.
