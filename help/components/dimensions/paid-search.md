---
title: Búsqueda paga
description: Distingue las métricas de la búsqueda paga y la búsqueda natural.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Búsqueda paga

La dimensión &#39;Búsqueda paga&#39; permite mirar cualquier métrica y compararla entre búsqueda paga y búsqueda natural. Todas las demás visitas fuera de los motores de búsqueda se omiten. Esta dimensión es útil para comprender cómo se comparan los esfuerzos de búsqueda paga con la búsqueda orgánica.

## Rellenar esta dimensión con datos

El único requisito para que esta dimensión funcione correctamente es tener la detección [de búsqueda](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga configurada correctamente en la configuración del grupo de informes. Si la detección de búsqueda paga está configurada correctamente y un grupo de informes tiene datos, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen dos valores estáticos: `"Natural"` y `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y también con la detección de búsqueda paga, pertenece al elemento de `"Paid"` dimensión. Si una visita coincide con los criterios de un motor de búsqueda y *no coincide con* la detección de búsqueda paga, pertenece al elemento de `"Natural"` dimensión.
