---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se ha establecido o persistido en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: ht
source-wordcount: '197'
ht-degree: 100%

---

# Vistas de páginas

La métrica **[!UICONTROL Vistas de página]** muestra el número de veces que un elemento de dimensión determinado (valor de dimensión) se ha definido o persistido (es decir, cuando caduca) en una página. [](overview.md) Es una de las métricas más comunes y básicas de los informes.

Por ejemplo, la dimensión [!UICONTROL Días de la semana] está compuesta por los siguientes elementos de dimensión: domingo, lunes, martes, miércoles, jueves, viernes y sábado.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos del resumen [Fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página frente a [Visitas](visits.md)**: vistas de página cuenta la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones de los visitantes. Una visita puede consistir en una o más vistas de página.
* **Vistas de página frente a [ Eventos de página](page-events.md)**: vistas de página cuenta el número de llamadas de seguimiento de vistas de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.
