---
title: Clasificación de todas las páginas de búsqueda
description: Determinar en qué página de un motor de búsqueda hizo clic un visitante en el sitio.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: 'https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 62%
---
# Clasificación de todas las páginas de búsqueda

La &quot;Clasificación de todas las páginas de búsqueda&quot; [dimension](overview.md) proporciona a insight en qué página de resultados de búsqueda hizo clic un visitante en su sitio. Por ejemplo, si su sitio aparece en la segunda página de los resultados de búsqueda de un motor de búsqueda, el elemento de dimensión para esta variable es “Página de búsqueda 2”.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del motor de búsqueda [referente](referrer.md) de cada visita, y determina en qué página de resultados de búsqueda hizo clic el visitante. No hay ninguna variable que establecer. Para que esta dimensión funcione solo es necesario que el grupo de informes tenga correctamente configurados los [Filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md).

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del referente del motor de búsqueda) |
| **Campo Web SDK / XDM** | Ninguno (derivado del referente del motor de búsqueda) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Si un visitante hace clic en su sitio desde un motor de búsqueda, el valor de esta dimensión es “Página de búsqueda” seguida del número de página en el que hizo clic. Si un hit no se origina desde un motor de búsqueda, el valor de esta dimensión es “No especificado”.
