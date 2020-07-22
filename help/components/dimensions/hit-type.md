---
title: Tipo de visita
description: Determina si la visita fue una visita en primer o segundo plano.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# Tipo de visita

La dimensión &#39;Tipo de visita&#39; determina si una aplicación móvil estaba en primer o segundo plano cuando la visita se envió a los servidores de recopilación de datos de Adobe. Esta dimensión solo es relevante para los grupos de informes que contienen datos para aplicaciones móviles. Los datos del explorador recopilados mediante AppMeasurement siempre informan de la visita como &quot;Primer plano&quot;.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones de SDK móvil en la versión 4.13.6 o superior. Si no utiliza el SDK móvil, todas las visitas a la lista en el elemento de dimensión &quot;Primer plano&quot;. If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Elementos de dimensión

Los elementos de dimensión incluyen `"Foreground"` y `"Background"`. Cualquier visita individual que no se haya enviado en segundo plano de una aplicación móvil pertenece al elemento de `"Foreground"` dimensión. Cualquier visita enviada donde la aplicación móvil estaba en segundo plano pertenece al elemento de `"Background"` dimensión.
