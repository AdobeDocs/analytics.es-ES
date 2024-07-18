---
title: Preguntas frecuentes sobre Data Warehouse
description: Preguntas frecuentes sobre Data Warehouse.
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 84%

---

# Preguntas frecuentes sobre Data Warehouse

Preguntas frecuentes sobre Data Warehouse.

## Cuando utilizo la lista desplegable de granularidad al crear una solicitud, ¿en qué formato puedo esperar que estén las fechas?

Al aplicar la granularidad en una solicitud de Data Warehouse, se añade la columna Fecha al informe. Según la granularidad seleccionada, el formato de fecha cambia.

| Granularidad | Formato | Ejemplo |
| --- | --- | --- |
| Por hora | `mmmm d, yyyy` Hora `H` | 1 de enero de 20XX, hora 0 |
| Diario | `mmmm d, yyyy` | 1 de enero de 20XX |
| Semanal | Semana `w, yyyy` | Semana 1, 20XX |
| Mensual | `mmmm yyyy` | Enero de 20XX |
| Trimestral | `q` Trimestre `yyyy` | Primer trimestre de 20XX |
| Anual | `yyyy` | 20XX |

## ¿Cómo funcionan los segmentos como dimensiones en Data Warehouse?

Cuando se utiliza un segmento como dimensión en Data Warehouse, el informe devuelve una columna que contiene `"0"` o `"1"`:

* **`"0"`**: El elemento de dimensión no cumplía los criterios del segmento.
* **`"1"`**: El elemento de dimensión cumplía los criterios del segmento.
