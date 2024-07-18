---
title: Longitud promedio de la sesión (móvil)
description: Longitud promedio de sesión del dispositivo móvil.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# Longitud promedio de la sesión (móvil)

La &quot;Longitud promedio de sesión (móvil)&quot; [métrica](overview.md) muestra la cantidad promedio de tiempo que un elemento de dimensión dado está presente por elemento de dimensión. Es similar a la métrica [[!UICONTROL Tiempo empleado por visita (segundos)]](time-spent-per-visit.md), excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cómo se calcula esta métrica

Esta métrica se calcula usando [métricas del ciclo vital](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
