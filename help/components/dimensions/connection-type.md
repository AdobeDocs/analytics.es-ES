---
title: Tipo de conexión
description: Conexión del visitante a Internet.
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# Tipo de conexión

La dimensión &quot;Tipo de conexión&quot; muestra cómo se conectó el visitante a Internet. Esta dimensión es útil para determinar cómo se conectan los visitantes a Internet para examinar el sitio. Puede utilizarla para optimizar el contenido del sitio en función de la velocidad de conexión de los visitantes.

## Rellene esta dimensión con datos

Esta dimensión utiliza una combinación de la [`ct` cadena de consulta](/help/implement/validate/query-parameters.md) y la lógica Adobe del lado del servidor. Adobe utiliza las siguientes reglas para determinar su valor:

1. Si la cadena de consulta `ct` es igual a `"modem"`, establezca el elemento de dimensión en `"Modem"`. AppMeasurement solo recopila estos datos en exploradores Internet Explorer no compatibles, lo que hace que este elemento de dimensión sea poco común.
1. Compruebe la dirección IP de la visita y haga referencia a una tabla de búsqueda interna del Adobe. Si la dirección IP es de un operador de telefonía móvil, establezca el elemento de dimensión en `"Mobile Carrier"`.
1. Si la cadena de consulta `ct` es igual a `"lan"`, establezca el elemento de dimensión en `"LAN/Wifi"`.
1. Si la visita se origina desde una [Fuente de datos](/help/import/c-data-sources/datasrc-home.md) o se considera de otro modo un tipo especial de visita, establezca el elemento de dimensión en `"Not specified"`.
1. Si no se cumple ninguna de las reglas anteriores, el valor predeterminado es `"LAN/Wifi"`.

## Elementos de dimensión

Los elementos de Dimension incluyen `LAN/Wifi`, `Mobile Carrier`, `Modem` y `Not Specified`.

* **`LAN/Wifi`**: El visitante se conectó a Internet a través de una línea fija o zona WiFi.
* **`Mobile Carrier`**: El visitante se conectó a Internet a través de un operador de telefonía móvil.
* **`Modem`**: El visitante se conectó a Internet mediante un módem en un explorador Internet Explorer no compatible.
* **`Not Specified`**: La visita no tenía un tipo de conexión.
