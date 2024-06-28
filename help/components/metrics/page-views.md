---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se ha establecido o persistido en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 46%

---

# Vistas de páginas

El **[!UICONTROL Page views]** [métrica](overview.md) muestra el número de veces que un elemento de dimensión determinado se estableció o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se establece o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos de [Fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página vs. [Visitas](visits.md)**: Las vistas de página cuentan la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones de los visitantes. Una visita consiste en una o más vistas de página.
* **Vistas de página vs. [Eventos de página](page-events.md)**: las vistas de página cuentan el número de llamadas de seguimiento de vista de página (`t()`) y excluyen las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.
