---
title: 'Longitud promedio de la sesión (móvil) '
description: Duración media de sesión del dispositivo móvil.
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# Longitud promedio de la sesión (móvil)


La métrica &#39;Longitud promedio de sesión (móvil)&#39; muestra la cantidad promedio de tiempo que un valor de dimensión dado está presente por valor de dimensión. Es similar a la métrica Tiempo [promedio en el sitio](average-time-on-site.md) , excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cómo se calcula esta métrica

Esta métrica se calcula usando las métricas [](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) móviles `'Total session length' / ('Launches' - 'First launches'`.
