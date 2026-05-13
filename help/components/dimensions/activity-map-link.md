---
description: El nombre del vínculo en el que se hizo clic.
title: Vínculo de Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 8%

---

# Vínculo de Activity Map

El &quot;vínculo de Activity Map&quot; [dimension](overview.md) muestra los vínculos más populares en los que se hizo clic. Puede utilizar esta dimensión para comparar qué vínculos del sitio se utilizan más, independientemente de dónde se hizo clic en los vínculos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Si su implementación utiliza [Activity Map](/help/analyze/activity-map/overview.md), esta variable de datos de contexto recopila datos automáticamente cuando se hace clic en los vínculos.

Para un vínculo determinado en el que se hizo clic, Activity Map busca lo siguiente (en orden):

1. La variable `s_objectID`
1. El texto interno del vínculo
1. Atributo `alt` para imágenes
1. El atributo `title`
1. Atributo `src` para imágenes
1. Atributo `action` para formularios

Si el elemento en el que se hizo clic no contiene ninguno de los criterios anteriores, Activity Map no recopila datos para ese clic.

## Elementos de dimensión

Los elementos de Dimension incluyen el texto del vínculo u otros atributos del vínculo en los que hacen clic los visitantes. La estructura y la implementación del sitio de su organización determinan los valores exactos recopilados.
