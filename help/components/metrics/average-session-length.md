---
title: Longitud promedio de la sesión (móvil)
description: Longitud promedio de sesión del dispositivo móvil.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 26%

---

# Longitud promedio de la sesión (móvil)

La &quot;Longitud promedio de sesión (móvil)&quot; [métrica](overview.md) muestra la cantidad promedio de tiempo que un elemento de dimensión determinado está presente por elemento de dimensión. Es similar a la [[!UICONTROL Tiempo empleado por visita (segundos)]](time-spent-per-visit.md) , excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cálculo de esta métrica

Esta métrica se calcula mediante la variable [Métricas del ciclo vital](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
