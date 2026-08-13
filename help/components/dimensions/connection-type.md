---
title: Tipo de conexión
description: Conexión del visitante a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 236
ht-degree: 94%

---

# Tipo de conexión

El &quot;Tipo de conexión&quot; [dimension](overview.md) muestra cómo se conectó el visitante a Internet. Esta dimensión es útil para determinar cómo se conectan los visitantes a internet para examinar el sitio. Puede utilizarla para optimizar el contenido del sitio en función de la velocidad de conexión de los visitantes.

## Rellene esta dimensión con datos

Esta dimensión utiliza una combinación de la [`ct` cadena de consulta](/help/implement/validate/query-parameters.md) y la lógica del lado del servidor de Adobe. Adobe utiliza las siguientes reglas para determinar su valor:

1. Si la cadena de consulta `ct` es igual a `"modem"`, establezca el elemento de dimensión en `"Modem"`. AppMeasurement solo recopila estos datos en exploradores como Internet Explorer no compatibles, lo que hace que este elemento de dimensión sea poco común.
1. Compruebe la dirección IP de la visita y haga referencia a una tabla de búsqueda interna de Adobe. Si la dirección IP es de un operador de telefonía móvil, establezca el elemento de dimensión en `"Mobile Carrier"`.
1. Si la cadena de consulta `ct` es igual a `"lan"`, establezca el elemento de dimensión en `"LAN/Wifi"`.
1. Si la visita se origina desde una [Fuente de datos](/help/import/data-sources/overview.md) o se considera de otro modo un tipo especial de visita, establezca el elemento de dimensión en `"Not specified"`.
1. Si no se cumple ninguna de las reglas anteriores, el valor predeterminado es `"LAN/Wifi"`.

## Elementos de dimensión

Los elementos de dimensión incluyen `LAN/Wifi`, `Mobile Carrier`, `Modem` y `Not Specified`.

* **`LAN/Wifi`**: el visitante se conectó a internet a través de una línea fija o zona WiFi.
* **`Mobile Carrier`**: el visitante se conectó a Internet a través de un operador de telefonía móvil.
* **`Modem`**: el visitante se conectó a Internet mediante un módem en un explorador Internet Explorer no compatible.
* **`Not Specified`**: la visita no tenía un tipo de conexión.
