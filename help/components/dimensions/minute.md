---
title: Minuto
description: El minuto en el que se produjo la métrica.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 91%

---

# Minuto

La dimensión [Minuto](overview.md) indica el minuto en el que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es el primer minuto del intervalo de fechas y el último elemento de dimensión es el último minuto del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo. Dada la granularidad de esta dimensión, Adobe recomienda limitar el intervalo de fechas de creación de informes a uno o dos días.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen un minuto determinado dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:MM YYYY-MM-DD`. Los elementos de dimensión que comienzan por `00:00` equivalen a medianoche de ese día, mientras que los valores que comienzan por `23:59` equivalen a las 11:59 PM de ese día.
