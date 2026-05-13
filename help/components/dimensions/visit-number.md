---
title: Número de visita
description: La enésima visita del visitante.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# Número de visita

Los informes de [dimensión](overview.md) “Número de visita” en los que se encuentra actualmente el visitante. Cuando se inicia una nueva visita, este elemento de dimensión aumenta en 1. Esta dimensión es útil cuando desea comprender el nivel de participación de los visitantes al regresar al sitio. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita y no puede cambiar. Se aplica a la duración del visitante, independientemente del intervalo de fechas del proyecto.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Visit number"` seguida de la representación numérica de la visita en la que se encuentra el visitante. Por ejemplo, si el visitante nunca antes había estado en el sitio, su primera visita pertenece al elemento de dimensión `"Visit number 1"`. Si esta es la 13.ª visita del visitante a su sitio, pertenecen al elemento de dimensión `"Visit number 13"`.
