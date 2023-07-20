---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se estableció o persistió en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 18%

---

# Vistas de páginas

El **[!UICONTROL Page views]** Esta métrica muestra el número de veces que un elemento de dimensión determinado (valor de dimensión) se definió o persistió (es decir, cuando caduca) en una página. Es una de las métricas más comunes y básicas de los informes.

Por ejemplo, la variable [!UICONTROL Días de la semana] Esta dimensión está compuesta por los siguientes elementos de dimensión: domingo, lunes, martes, miércoles, jueves, viernes y sábado.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos del resumen [Fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página vs. [Visitas](visits.md)**: Las vistas de página cuentan la cantidad de veces que se ve una página. Las visitas cuentan el número de sesiones de los visitantes. Una visita puede consistir en una o más vistas de página.
* **Vistas de página vs. [Eventos de página](page-events.md)**: las vistas de página cuentan el número de llamadas de seguimiento de vista de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.
