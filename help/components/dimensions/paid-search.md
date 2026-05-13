---
title: Búsqueda de pago
description: Distingue las métricas de la búsqueda de pago y la búsqueda natural.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 87%

---

# Búsqueda de pago

La [dimensión](overview.md) &quot;Búsqueda de pago&quot; le permite ver cualquier métrica y compararla entre la búsqueda de pago y la búsqueda natural. Se omiten todas las demás visitas fuera de los motores de búsqueda. Esta dimensión es útil para comprender cómo se comparan los esfuerzos de búsqueda de pago con la búsqueda orgánica.

## Rellene esta dimensión con datos

El único requisito para que esta dimensión funcione correctamente es tener la [detección de búsqueda de pago](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) configurada correctamente en la configuración del grupo de informes. Si la detección de búsqueda de pago está configurada correctamente y el grupo de informes tiene datos, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen dos valores estáticos: `"Natural"` y `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y también con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y *no* coincide con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Natural"`.
