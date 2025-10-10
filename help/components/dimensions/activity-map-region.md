---
title: Región de Activity Map
description: Región del sitio en la que se hizo clic.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Región de Activity Map

La [dimensión](overview.md) &quot;Región de Activity Map&quot; muestra las regiones del sitio en las que se hizo clic con mayor frecuencia. Esta dimensión es útil cuando desea comparar clics en regiones generales del sitio en lugar de vínculos individuales. También resulta útil para áreas del sitio que sirven contenido dinámico. Por ejemplo, si tiene una página principal con artículos de noticias que giran, el uso de la dimensión [Vínculo de Activity Map](activity-map-link.md) sería difícil porque el texto del vínculo cambia constantemente. Sin embargo, dado que esos vínculos utilizan la misma región, puede analizar el rendimiento de esa área aunque los vínculos individuales cambien cada día.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Si su implementación utiliza [Activity Map](/help/analyze/activity-map/overview.md), esta variable de datos de contexto recopila datos automáticamente cuando se hace clic en los vínculos.

Para un vínculo determinado en el que se hizo clic, compruebe el elemento DOM principal en busca de lo siguiente (en orden):

* Un valor en el atributo establecido por [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - establecido en el atributo `id` de forma predeterminada
* Un valor en el atributo `aria-label` cuando el atributo `role="region"`
* Los elementos semánticos `<header>`, `<main>`, `<footer>` o `<nav>` (solo Web SDK)

Si el elemento DOM principal no cumple ninguno de los criterios anteriores, la búsqueda continúa de forma recursiva hacia arriba en la jerarquía DOM. Si no se encuentran elementos coincidentes, se devuelve el valor `BODY`.

## Elementos de dimensión

Los elementos de Dimension incluyen regiones que ha etiquetado en el sitio. Los valores de región específicos dependen de los atributos que se utilicen y de si hay elementos HTML semánticos presentes.
