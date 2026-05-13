---
title: Profundidad de la visita
description: Dimensión basada en visitas que indica la profundidad de la visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 90%

---

# Profundidad de la visita

La &quot;Profundidad de la visita&quot; [dimension](overview.md) indica la cantidad de vistas de página que vio el visitante en toda la visita. La profundidad de la visita solo aumenta si la visita es una vista de página y la dimensión [Página](page.md) no es la misma que el elemento de dimensión de la última vista de página. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todas las visitas de una visita después de que la visita finalice.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Pages per visit"` seguida de un número que representa el número de páginas en la visita. El elemento de dimensión de `"Pages per visit: 1"` representa una visita de una sola página, mientras que el elemento de dimensión `"Pages per visit: 8"` representa una visita con 8 vistas de página (y cualquier número de llamadas de seguimiento de vínculos).

## Comparación con la profundidad de la visita

Consulte [Profundidad de la visita](hit-depth.md) para ver una comparación entre dimensiones.
