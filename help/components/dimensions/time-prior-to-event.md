---
title: Tiempo previo al evento
description: Cantidad de tiempo entre la métrica y la primera visita individual de la visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 84%

---

# Tiempo previo al evento

La [dimensión](overview.md) &quot;Tiempo previo al evento&quot; indica la cantidad de tiempo que transcurrió entre la primera visita individual de la visita y la métrica deseada. Esta dimensión es útil para determinar la cantidad de tiempo que se tarda en alcanzar un evento de éxito, como un envío de formulario o una compra.

## Rellene esta dimensión con datos

Aunque técnicamente esta dimensión funciona de forma predeterminada para todas las implementaciones, funciona mejor con eventos personalizados y de compra. Adobe recomienda implementar eventos personalizados en el sitio. Si implementa eventos personalizados, no se requiere una implementación adicional para esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen bloques basados en tiempo que van desde `"Less than 1 minute"` hasta `"More than 15 hours"`. Por ejemplo, si un visitante tardase 23 minutos desde su primera visita hasta que realiza una compra, pertenecería al elemento de dimensión `"10 to 30 minutes"`. Los contenedores no se pueden personalizar para esta métrica.
