---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se estableció o persistió en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 1be9a8ceb03f8102a0799f4518db35c1e8cd7b14
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 33%

---

# Vistas de páginas

La métrica “Vistas de página” muestra el número de veces que un elemento de dimensión determinado se estableció o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos del resumen [Fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página vs. [Visitas](visits.md)**: Las vistas de página cuentan la cantidad de veces que se ve una página. Las visitas cuentan el número de sesiones de los visitantes. Una visita consiste en una o más vistas de página.
* **Vistas de página vs. [Eventos de página](page-events.md)**: Las vistas de página cuentan el número de llamadas de seguimiento de vista de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.
