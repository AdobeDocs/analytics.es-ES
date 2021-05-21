---
title: Longitud promedio de la sesión (móvil)
description: Longitud promedio de sesión del dispositivo móvil.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '83'
ht-degree: 100%

---

# Longitud promedio de la sesión (móvil)

La métrica “Longitud promedio de sesión (móvil)” muestra la cantidad promedio de tiempo que un elemento de dimensión dado está presente por elemento de dimensión. Es similar a la métrica [Tiempo promedio en el sitio](average-time-on-site.md), excepto que esta métrica utiliza componentes específicos del SDK móvil como parte de su cálculo.

## Cálculo de esta métrica

Esta métrica se calcula usando las [métricas móviles](https://docs.adobe.com/content/help/es-ES/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
