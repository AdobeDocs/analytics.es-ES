---
title: Longitud promedio de la sesión (móvil)
description: Longitud promedio de sesión del dispositivo móvil.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 41%

---

# Longitud promedio de la sesión (móvil)

La &quot;Longitud promedio de sesión (móvil)&quot; [métrica](overview.md) muestra la cantidad promedio de tiempo que un elemento de dimensión determinado está presente por elemento de dimensión. Es similar a la [Tiempo empleado por visita [segundos]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) , excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cálculo de esta métrica

Esta métrica se calcula usando las [métricas móviles](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=es) `'Total session length' / ('Launches' - 'First launches'`.
