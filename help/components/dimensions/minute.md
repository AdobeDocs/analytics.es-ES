---
title: Minuto
description: El minuto en el que se produjo la métrica.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 76%

---

# Minuto

La dimensión [Minuto](overview.md) indica el minuto en el que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es el primer minuto del intervalo de fechas y el último elemento de dimensión es el último minuto del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo. Dada la granularidad de esta dimensión, Adobe recomienda limitar el intervalo de fechas de creación de informes a uno o dos días.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen un minuto determinado dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:MM YYYY-MM-DD`. Los elementos de Dimension que comienzan por `00:00` equivalen a medianoche de ese día, mientras que los valores que comienzan por `23:59` equivalen a las 11:59 PM de ese día.
