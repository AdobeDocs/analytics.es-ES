---
title: Vínculo de Activity Map por región
description: Un valor concatenado de vínculo y región.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Vínculo de Activity Map por región

La [dimensión](overview.md) &quot;Vínculo de Activity Map por región&quot; muestra una concatenación de [Vínculo de Activity Map](activity-map-link.md) y [Región de Activity Map](activity-map-link-by-region.md). Esta dimensión es útil cuando tiene vínculos con nombres similares, pero que residen en diferentes regiones del sitio. Por ejemplo, si tiene varios vínculos a la página principal con la etiqueta &quot;Inicio&quot;, puede utilizar esta dimensión para distinguir esos vínculos en cada región del sitio.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de las [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` y `c.a.activitymap.region`. Estos dos valores están concatenados y separados por una barra vertical (`|`). Si su implementación usa [Activity Map](/help/analyze/activity-map/overview.md), estas variables de datos de contexto recopilan datos automáticamente cuando se hace clic en los vínculos.

## Elementos de dimensión

Los elementos de Dimension incluyen valores de [Activity Map Link](activity-map-link.md) y [Activity Map Region](activity-map-link-by-region.md). La estructura y la implementación del sitio de su organización determinan los valores exactos recopilados.
