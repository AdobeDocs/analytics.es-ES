---
title: 'Métrica Vistas de página explicada | Adobe Analytics '
description: Conozca cómo se ha desarrollado la métrica de vistas de página en Adobe Analytics, y descubra la diferencia entre las vistas de página y las visitas.
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---

# Obtenga información acerca de Vistas de página con Adobe Analytics

La métrica “Vistas de página” muestra el número de veces que un elemento de dimensión determinado se estableció o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas individuales en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparar con métricas similares

* **Vistas de página vs. [Visitas](visits.md)**: vistas de página cuenta la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones de los visitantes. Una visita consiste en una o más páginas.
* **Vistas de página vs. [Eventos de página](page-events.md)**: vistas de página cuenta el número de llamadas de seguimiento de vistas de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Eventos de página es lo contrario; cuenta el número de llamadas de seguimiento de vínculos y excluye las vistas de página.
