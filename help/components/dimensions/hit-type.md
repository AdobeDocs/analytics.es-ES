---
title: Tipo de visita
description: Determina si la visita fue una visita en primer o segundo plano.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# Tipo de visita

La dimensión &#39;Tipo de visita&#39; determina si una aplicación móvil estaba en primer o segundo plano cuando la visita se envió a los servidores de recopilación de datos de Adobe. Esta dimensión solo es relevante para los grupos de informes que contienen datos para aplicaciones móviles. Los datos del explorador recopilados mediante AppMeasurement siempre informan de la visita como &quot;Primer plano&quot;.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones de SDK móvil en la versión 4.13.6 o superior. Si no utiliza el SDK móvil, todas las visitas a la lista bajo el valor de dimensión &quot;Primer plano&quot;. If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Valores de dimensión

Los valores de dimensión incluyen `"Foreground"` y `"Background"`. Cualquier visita individual que no se haya enviado en el fondo de una aplicación móvil pertenece al valor de la `"Foreground"` dimensión. Cualquier visita enviada donde la aplicación móvil estaba en segundo plano pertenece al valor de la `"Background"` dimensión.
