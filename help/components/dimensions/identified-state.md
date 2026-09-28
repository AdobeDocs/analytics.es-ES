---
title: Estado identificado
description: Un indicador que determina el reconocimiento para la vinculación.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: 'https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 46%
---
# Estado identificado

El &quot;estado identificado&quot; [dimensión](overview.md) es específico de los grupos de informes virtuales de [Cross-Device Analytics](../cda/overview.md). Notifica si el sistema identifica (vincula) los hits o no en el momento en que se ejecuta el informe. Esta dimensión es útil para comprender cómo comprime datos o vincula datos CDA.

## Rellene esta dimensión con datos

[Análisis entre dispositivos](../cda/overview.md) calcula esta dimensión cuando se ejecuta un informe, en función de si cada visita se vinculó a una persona. Siempre que Análisis entre dispositivos esté configurado para un grupo de informes virtuales, funcionará de forma predeterminada; no hay ninguna variable que establecer.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Análisis entre dispositivos) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Análisis entre dispositivos) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**: el hit se asigna a una persona.
* **`"Unidentified"`**: el hit no está asignado a una persona y no se ha podido asignar mediante ningún método de atribución.
