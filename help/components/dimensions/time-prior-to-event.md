---
title: Tiempo previo al evento
description: Cantidad de tiempo entre la métrica y el primer hit de la visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: 'https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0'
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
source-wordcount: '197'
ht-degree: 53%
---
# Tiempo previo al evento

La [dimensión](overview.md) &quot;Tiempo previo al evento&quot; indica la cantidad de tiempo que transcurrió entre la primera visita individual de la visita y la métrica deseada. Esta dimensión es útil para determinar la cantidad de tiempo que se tarda en alcanzar un evento de éxito, como un envío de formulario o una compra.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor a partir del tiempo transcurrido entre la primera visita individual de la visita y el evento de destinatario. No hay ninguna variable que establecer. Aunque técnicamente funciona de forma predeterminada, funciona mejor cuando los eventos personalizados y de compra se implementan en el sitio.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen bloques basados en tiempo que van desde `"Less than 1 minute"` hasta `"More than 15 hours"`. Por ejemplo, si un visitante tardase 23 minutos desde su primer hit hasta que realiza una compra, pertenecería al elemento de dimensión `"10 to 30 minutes"`. Los contenedores no se pueden personalizar para esta métrica.
