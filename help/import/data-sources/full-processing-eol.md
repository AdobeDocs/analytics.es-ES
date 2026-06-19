---
title: Fin de la vida útil de las fuentes de datos de procesamiento completo
description: Obtenga más información sobre el anuncio de fin de vida útil para fuentes de datos de procesamiento completo.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
TQID: 'https://experienceleague.adobe.com/3NSbjRWl0GsomjsEXo8XczQ1RWOPGpqW4OM2YeUo3Wk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 8%

---

# Fin de la vida útil de las fuentes de datos de procesamiento completo

Históricamente, las fuentes de datos de procesamiento completo han permitido a las organizaciones enviar datos de nivel de visita a Adobe Analytics. Estos datos se procesaron del mismo modo que los datos recopilados a través de medios tradicionales de recopilación de datos, como AppMeasurement. En 2020, Adobe lanzó la [API de inserción masiva de datos](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que realiza las mismas funciones que las fuentes de datos de procesamiento completo, pero con características adicionales. Esta página proporciona detalles sobre la funcionalidad adicional proporcionada por la API de inserción de datos en lote y describe las diferencias en los formatos de archivo.

El 25 de marzo de 2021, Adobe impidió que se crearan nuevas conexiones de fuentes de datos de procesamiento completo. El 31 de enero de 2022, se desactivaron todos los servicios de procesamiento completo de datos.

## Diferencias clave entre las fuentes de datos de procesamiento completo y la API de inserción de datos en lote

* La inserción de datos en lote permite enviar varios archivos para un procesamiento paralelo. Los grupos de visitantes garantizan la continuidad del visitante y la atribución de eVar.
* La inserción de datos en lote tiene funcionalidades de validación de datos y gestión de errores, lo que elimina parte del trabajo administrativo del envío de datos de visitas.
* La inserción de datos en lote admite varios métodos de identificación de ID de visitante.
* La inserción de datos en lote tiene algunos campos obligatorios adicionales: Una columna de identificación de visitante, un `pageName` (o vínculo equivalente), `reportSuiteID`, `timestamp` y `userAgent`.
* Para garantizar la continuidad y la atribución del visitante, la inserción de datos en lote requiere que las filas de los archivos se ordenen en orden cronológico. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para obtener más información sobre el orden de la actividad del visitante en todos los archivos.
* La inserción de datos en lote requiere que los archivos estén comprimidos en .csv en formato .gzip.
* BDIA usa `timestamp` en lugar de `date`.

## Comparación de variables entre BDIA y fuentes de datos de procesamiento completo

Las siguientes variables se introdujeron para la inserción de datos en lote, que antes no estaba disponible en las fuentes de datos de procesamiento completo:

* **`aamlh`**: sugerencia de ubicación de Adobe Audience Manager.
* **`contextData.key`**: [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: variables del servicio de Experience Cloud ID. Incluye `id`, `authState`y `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variables. Incluye `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion` y `wow64`.
* **`ipaddress`**: la dimensión [dirección IP](/help/components/dimensions/ip-address.md).
* **`language`**: La dimensión [Idioma](/help/components/dimensions/language.md).
* **`list1`** - **`list3`**: [Variables de lista](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: el Experience Cloud ID del visitante.
* **`tnta`**: carga de datos de destino usada en integraciones de [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=es).
* **`trackingServer`**: la variable [`trackingServer`](/help/implement/vars/config-vars/configuration-variables.md).
* **`transactionID`**: la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **`userAgent`**: la cadena del agente de usuario del dispositivo.

Las siguientes variables no son compatibles mediante la inserción de datos en lote:

* **`charSet`**: la variable [`charSet`](/help/implement/vars/config-vars/charset.md). La inserción de datos en lote solo admite UTF-8.
* **`timezone`**: diferencia horaria entre la zona horaria del visitante y GMT, en horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: variables utilizadas en la recopilación de datos de Activity Map.
