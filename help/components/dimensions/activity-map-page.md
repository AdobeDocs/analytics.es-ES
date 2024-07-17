---
title: Página de Activity Map
description: Nombre de la página cuando se hizo clic en un vínculo.
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Página de Activity Map

La &quot;Página de Activity Map&quot; [dimension](overview.md) muestra la página en la que se encontraba un visitante cuando se hizo clic en un vínculo. Puede utilizar esta dimensión para determinar qué páginas contienen vínculos en los que se hace clic con mayor frecuencia. La superposición de Activity Map también utiliza esta dimensión para determinar qué vínculos mostrar.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Si su implementación utiliza [Activity Map](/help/analyze/activity-map/overview.md), esta variable de datos de contexto recopila datos automáticamente cuando se hace clic en los vínculos.

Para un vínculo determinado en el que se hizo clic, esta variable de datos de contexto recopila el valor en la dimensión [Página](page.md). Si la dimensión Página no contiene un valor, se utiliza la dimensión [Dirección URL de la página](page-url.md) en su lugar (de manera similar a la reserva que utiliza la dimensión Página). Los datos del Activity Map generalmente se envían en la siguiente visita después de hacer clic en un vínculo. Esta dimensión le permite determinar el valor de página cuando se hizo clic en el vínculo, en lugar del valor de página cuando se enviaron los datos.

## Elementos de dimensión

Los elementos del Dimension incluyen todos los valores encontrados en la dimensión [Página](page.md).
