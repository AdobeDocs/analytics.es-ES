---
title: Tipo de visita
description: Determina si la visita fue una visita en primer o segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 84%

---

# Tipo de visita

El &quot;Tipo de visita&quot; [dimension](overview.md) determina si una aplicación móvil estaba en primer o segundo plano cuando la visita se envió a los servidores de recopilación de datos de Adobe. Esta dimensión solo es relevante para los grupos de informes que contienen datos para aplicaciones móviles. Los datos del explorador recopilados con AppMeasurement siempre informan de la visita como “Primer plano”.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones de SDK móvil en la versión 4.13.6 o superior. Si no utiliza el SDK móvil, todas las visitas se enumeran en el elemento de dimensión “Primer plano”. Si la opción “Deshabilitar informes y atribuciones anteriores para visitas en segundo plano” está activada, las visitas individuales en segundo plano solo aparecerán en el [Grupo de informes virtual](../vrs/vrs-mobile-visit-processing.md).

## Elementos de dimensión

Los elementos de dimensión incluyen `"Foreground"` y `"Background"`. Cualquier visita individual que no se haya enviado en segundo plano de una aplicación móvil pertenece al elemento de dimensión `"Foreground"`. Cualquier visita enviada donde la aplicación móvil estaba en segundo plano pertenece al elemento de dimensión `"Background"`.
