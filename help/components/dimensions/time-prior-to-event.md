---
title: Tiempo previo al evento
description: Cantidad de tiempo entre la métrica y la primera visita individual de la visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---

# Tiempo previo al evento

La dimensión “Tiempo previo al evento” indica la cantidad de tiempo que transcurrió entre la primera visita y la métrica deseada. Esta dimensión es útil para determinar la cantidad de tiempo que se tarda en alcanzar un evento de éxito, como un envío de formulario o una compra.

## Rellene esta dimensión con datos

Aunque técnicamente esta dimensión funciona de forma predeterminada para todas las implementaciones, funciona mejor con eventos personalizados y de compra. Adobe recomienda implementar eventos personalizados en el sitio. Si implementa eventos personalizados, no se requiere una implementación adicional para esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen bloques basados en tiempo que van desde `"Less than 1 minute"` hasta `"More than 15 hours"`. Por ejemplo, si un visitante tardase 23 minutos desde su primera visita hasta que realiza una compra, pertenecería al elemento de dimensión `"10 to 30 minutes"`. Los contenedores no se pueden personalizar para esta métrica.
