---
title: Longitud promedio de la sesión (móvil)
description: Longitud promedio de sesión del dispositivo móvil.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 65%

---

# Longitud promedio de la sesión (móvil)

La métrica “Longitud promedio de sesión (móvil)” muestra la cantidad promedio de tiempo que un elemento de dimensión dado está presente por elemento de dimensión. Es similar a la variable [Tiempo empleado por visita [segundos]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) , excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cálculo de esta métrica

Esta métrica se calcula usando las [métricas móviles](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=es) `'Total session length' / ('Launches' - 'First launches'`.
