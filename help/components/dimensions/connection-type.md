---
title: Tipo de conexión
description: Conexión del visitante a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
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
