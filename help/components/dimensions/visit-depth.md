---
title: Profundidad de la visita
description: Dimensión basada en visitas que indica la profundidad de la visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: 'https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 68%
---
# Profundidad de la visita

La &quot;Profundidad de la visita&quot; [dimension](overview.md) indica la cantidad de vistas de página que vio el visitante en toda la visita. La profundidad de la visita solo aumenta si el hit es una vista de página y la dimensión [Página](page.md) no es la misma que el elemento de dimensión de la última vista de página. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todos los hits de una visita después de que la visita finalice.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor a partir de las vistas de página de cada visita. No hay ninguna variable que establecer; funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Visita |

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Pages per visit"` seguida de un número que representa el número de páginas en la visita. El elemento de dimensión de `"Pages per visit: 1"` representa una visita de una sola página, mientras que el elemento de dimensión `"Pages per visit: 8"` representa una visita con 8 vistas de página (y cualquier número de llamadas de seguimiento de vínculos).

## Comparación con la profundidad del hit

Consulte [Profundidad del hit](hit-depth.md) para ver una comparación entre dimensiones.
