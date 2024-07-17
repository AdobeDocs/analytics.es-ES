---
description: El nombre del vínculo en el que se hizo clic.
title: Vínculo de Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Vínculo de Activity Map

El &quot;vínculo de Activity Map&quot; [dimension](overview.md) muestra los vínculos más populares en los que se hizo clic. Puede utilizar esta dimensión para comparar qué vínculos del sitio se utilizan más, independientemente de dónde se hizo clic en los vínculos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Si su implementación utiliza [Activity Map](/help/analyze/activity-map/overview.md), esta variable de datos de contexto recopila datos automáticamente cuando se hace clic en los vínculos.

Para un vínculo determinado en el que se hizo clic, el Activity Map busca lo siguiente (en orden):

1. La variable `s_objectID`
1. El texto interno del vínculo
1. Atributo `alt` para imágenes
1. El atributo `title`
1. Atributo `src` para imágenes
1. Atributo `action` para formularios

Si el elemento en el que se hizo clic no contiene ninguno de los criterios anteriores, Activity Map no recopila datos para ese clic.

## Elementos de dimensión

Los elementos del Dimension incluyen el texto del vínculo u otros atributos del vínculo en los que hacen clic los visitantes. La estructura y la implementación del sitio de su organización determinan los valores exactos recopilados.
