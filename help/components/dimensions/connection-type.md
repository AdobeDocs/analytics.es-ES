---
title: Tipo de conexión
description: Conexión del visitante a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 76%
---
# Tipo de conexión

El &quot;Tipo de conexión&quot; [dimension](overview.md) muestra cómo se conectó el visitante a Internet. Esta dimensión es útil para determinar cómo se conectan los visitantes a internet para examinar el sitio. Puede utilizarla para optimizar el contenido del sitio en función de la velocidad de conexión de los visitantes.

## Rellene esta dimensión con datos

Esta dimensión está determinada por una combinación de datos recopilados y lógica del lado del servidor de Adobe, no por una variable que haya configurado.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | [`ct`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<connectionType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | n/a |
| **Persistencia** | n/a |

Adobe utiliza las siguientes reglas para determinar su valor:

1. Si la cadena de consulta `ct` es igual a `"modem"`, establezca el elemento de dimensión en `"Modem"`. AppMeasurement solo recopila estos datos en exploradores como Internet Explorer no compatibles, lo que hace que este elemento de dimensión sea poco común.
1. Compruebe la dirección IP del hit y haga referencia a una tabla de búsqueda interna de Adobe. Si la dirección IP es de un operador de telefonía móvil, establezca el elemento de dimensión en `"Mobile Carrier"`.
1. Si la cadena de consulta `ct` es igual a `"lan"`, establezca el elemento de dimensión en `"LAN/Wifi"`.
1. Si el hit se origina desde una [Fuente de datos](/help/import/data-sources/overview.md) o se considera de otro modo un tipo especial de hit, establezca el elemento de dimensión en `"Not specified"`.
1. Si no se cumple ninguna de las reglas anteriores, el valor predeterminado es `"LAN/Wifi"`.

## Elementos de dimensión

Los elementos de dimensión incluyen `LAN/Wifi`, `Mobile Carrier`, `Modem` y `Not Specified`.

* **`LAN/Wifi`**: el visitante se conectó a internet a través de una línea fija o zona WiFi.
* **`Mobile Carrier`**: el visitante se conectó a Internet a través de un operador de telefonía móvil.
* **`Modem`**: el visitante se conectó a Internet mediante un módem en un explorador Internet Explorer no compatible.
* **`Not Specified`**: el hit no tenía un tipo de conexión.
