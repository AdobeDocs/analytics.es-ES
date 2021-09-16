---
title: Estado identificado
description: Un indicador que determina el reconocimiento por el gráfico del dispositivo.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 1a58c3e87f5918c91b891faa6027f5ad8b6024b9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 61%

---

# Estado identificado

La dimensión Estado identificado es específica de los grupos de informes virtuales de [Cross-Device Analytics](../cda/overview.md). Notifica si el sistema identifica (vincula) las visitas o no en el momento en que se ejecuta el informe. Esta dimensión es útil para comprender cómo comprime datos o vincula datos CDA.

## Rellene esta dimensión con datos

Siempre que tenga [Cross-Device Analytics](../cda/overview.md) configurado para un grupo de informes virtual, esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen `"Identified"` y `"Unidentified"`.

* **`"Identified"`**: La visita se asigna a una persona.
* **`"Unidentified"`**: La visita no está asignada a una persona y no se ha podido asignar mediante ningún método de atribución.
