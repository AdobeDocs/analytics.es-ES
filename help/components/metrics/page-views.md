---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se ha establecido o persistido en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---

# Vistas de páginas

La [métrica](overview.md) **[!UICONTROL Vistas de página]** muestra el número de veces que un elemento de dimensión determinado se estableció o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos de [fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página frente a [Visitas](visits.md)**: Vistas de página cuenta la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones de los visitantes. Una visita consiste en una o más vistas.
* **Vistas de página frente a [Eventos de página](page-events.md)**: Vistas de página cuenta el número de llamadas de seguimiento de vista de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.
