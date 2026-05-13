---
title: Página de Activity Map
description: Nombre de la página cuando se hizo clic en un vínculo.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Página de Activity Map

La &quot;Página Activity Map&quot; [dimension](overview.md) muestra la página en la que se encontraba un visitante cuando se hizo clic en un vínculo. Puede utilizar esta dimensión para determinar qué páginas contienen vínculos en los que se hace clic con mayor frecuencia. La superposición de Activity Map también utiliza esta dimensión para determinar qué vínculos mostrar.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Si su implementación utiliza [Activity Map](/help/analyze/activity-map/overview.md), esta variable de datos de contexto recopila datos automáticamente cuando se hace clic en los vínculos.

Para un vínculo determinado en el que se hizo clic, esta variable de datos de contexto recopila el valor en la dimensión [Página](page.md). Si la dimensión Página no contiene un valor, se utiliza la dimensión [Dirección URL de la página](page-url.md) en su lugar (de manera similar a la reserva que utiliza la dimensión Página). Los datos de Activity Map generalmente se envían en la siguiente visita después de hacer clic en un vínculo. Esta dimensión le permite determinar el valor de página cuando se hizo clic en el vínculo, en lugar del valor de página cuando se enviaron los datos.

## Elementos de dimensión

Los elementos de Dimension incluyen todos los valores encontrados en la dimensión [Página](page.md).
