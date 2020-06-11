---
title: Tiempo previo al evento
description: Cantidad de tiempo entre la métrica y la primera visita individual de la visita.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Tiempo previo al evento

La dimensión &#39;Tiempo previo al evento&#39; informa la cantidad de tiempo que transcurrió entre la primera visita y la métrica deseada. Esta dimensión es útil para determinar la cantidad de tiempo que se tarda en alcanzar un evento de éxito, como un envío de formulario o una compra.

## Rellenar esta dimensión con datos

Aunque técnicamente esta dimensión funciona de forma predeterminada para todas las implementaciones, funciona mejor con eventos personalizados y de compra. Adobe recomienda implementar eventos personalizados en el sitio. Si implementa eventos personalizados, no se requiere una implementación adicional para esta dimensión.

## Valores de dimensión

Los valores de dimensión incluyen bloques basados en tiempo que van desde `"Less than 1 minute"` hasta `"More than 15 hours"`. Por ejemplo, si tomara un visitante 23 minutos desde la primera visita a una compra, pertenecería al valor de la `"10 to 30 minutes"` dimensión.
