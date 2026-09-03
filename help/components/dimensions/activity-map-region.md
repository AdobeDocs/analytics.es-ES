---
title: Región de Activity Map
description: Región del sitio en la que se hizo clic.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 249
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
