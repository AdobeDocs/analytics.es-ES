---
title: Búsqueda de pago
description: Distingue las métricas de la búsqueda de pago y la búsqueda natural.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 87%

---

# Búsqueda de pago

La &quot;Búsqueda de pago&quot; [dimensión](overview.md) le permite mirar cualquier métrica y compararla entre la búsqueda de pago y la búsqueda natural. Se omiten todas las demás visitas fuera de los motores de búsqueda. Esta dimensión es útil para comprender cómo se comparan los esfuerzos de búsqueda de pago con la búsqueda orgánica.

## Rellene esta dimensión con datos

El único requisito para que esta dimensión funcione correctamente es tener la [detección de búsqueda de pago](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) configurada correctamente en la configuración del grupo de informes. Si la detección de búsqueda de pago está configurada correctamente y el grupo de informes tiene datos, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen dos valores estáticos: `"Natural"` y `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y también con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y *no* coincide con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Natural"`.
