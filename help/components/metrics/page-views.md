---
title: Vistas de páginas
description: El número de veces que se visualizó una página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# Vistas de páginas

La métrica &#39;vistas de página muestra el número de veces que un elemento de dimensión determinado se configuró o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cómo se calcula esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparar con métricas similares

* **vistas de página vs.[Visitas](visits.md)**: vistas de página cuenta la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones para visitantes. Una visita consiste en una o más páginas.
* **vistas de página vs. eventos[](page-events.md)**de página: vistas de página cuenta el número de llamadas de seguimiento de vista de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). eventos de página es lo contrario; cuenta el número de llamadas de seguimiento de vínculos y excluye las vistas de página.