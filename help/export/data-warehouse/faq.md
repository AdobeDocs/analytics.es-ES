---
title: Preguntas más frecuentes sobre Data Warehouse
description: Preguntas más frecuentes sobre Data Warehouse.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# Preguntas más frecuentes sobre Data Warehouse

Preguntas más frecuentes sobre Data Warehouse.

## Cuando uso la lista desplegable de granularidad al crear una solicitud, ¿en qué formato puedo esperar que estén las fechas?

Al aplicar la granularidad en una solicitud de Data Warehouse, se agrega la columna &#39;Fecha&#39; al informe. Según la granularidad seleccionada, el formato de fecha cambia.

| Granularidad | Formato | Ejemplo |
| --- | --- | --- |
| Por hora | `mmmm d, yyyy` Hora `H` | 1 de enero, 20 XX, hora 0 |
| Diaria | `mmmm d, yyyy` | 1 de enero, 20 XX |
| Semanal | Semana `w, yyyy` | Semana 1, 20XX |
| Mensual | `mmmm yyyy` | 20 de enero |
| Trimestral | `q` Trimestre `yyyy` | Primer trimestre 20XX |
| Anual | `yyyy` | 20XX |

## ¿Cómo funcionan los segmentos como dimensiones en la Data Warehouse?

Cuando se utiliza un segmento como dimensión en la Data Warehouse, el informe devuelve una columna que contiene `"0"` o `"1"`:

* **`"0"`**:: El elemento de dimensión no cumplía los criterios del segmento.
* **`"1"`**:: El elemento de dimensión cumple los criterios del segmento.
