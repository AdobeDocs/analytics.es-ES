---
title: Estado identificado
description: Un indicador que determina el reconocimiento para la vinculación.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 83%

---

# Estado identificado

El &quot;estado identificado&quot; [dimensión](overview.md) es específico de los grupos de informes virtuales de [Cross-Device Analytics](../cda/overview.md). Notifica si el sistema identifica (vincula) las visitas o no en el momento en que se ejecuta el informe. Esta dimensión es útil para comprender cómo comprime datos o vincula datos CDA.

## Rellene esta dimensión con datos

Siempre que tenga [Cross-Device Analytics](../cda/overview.md) configurado para un grupo de informes virtual, esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**: la visita se asigna a una persona.
* **`"Unidentified"`**: la visita no está asignada a una persona y no se ha podido asignar mediante ningún método de atribución.
