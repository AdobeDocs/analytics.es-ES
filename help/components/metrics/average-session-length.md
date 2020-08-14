---
title: 'Longitud promedio de la sesión (móvil) '
description: Longitud promedio de sesión del dispositivo móvil.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 74%

---


# Longitud promedio de la sesión (móvil)


La métrica &#39;Longitud promedio de sesión (móvil)&#39; muestra la cantidad promedio de tiempo que un elemento de dimensión dado está presente por elemento de dimensión. Es similar a la métrica [Tiempo promedio en el sitio](average-time-on-site.md), excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cálculo de esta métrica

Esta métrica se calcula usando las [métricas móviles](https://docs.adobe.com/content/help/es-ES/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
