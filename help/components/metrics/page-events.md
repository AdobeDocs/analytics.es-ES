---
title: Eventos de página
description: Número de acciones de seguimiento de vínculos activadas.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 33%

---

# Eventos de página

La [métrica](overview.md) &quot;Eventos de página&quot; muestra la cantidad de veces que se realizó una llamada de seguimiento de vínculo. Esta métrica es útil cuando desea comprender qué páginas tienen el contenido más atractivo. La medición para esta métrica es muy valiosa cuando un visitante puede realizar una acción en la página sin navegar a una nueva página.

Por ejemplo, en un recorrido típico de un sitio de comercio electrónico, un visitante puede tener varias interacciones en una sola página. Una implementación típica de Analytics tiene estas interacciones configuradas como una llamada de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)), mientras que una llamada de vista de páginas ([`t()`](/help/implement/vars/functions/t-method.md)) se reserva para la carga inicial de la página. Este método de implementación proporciona un seguimiento de eventos enriquecido que proporciona una perspectiva sobre las interacciones que se producen antes de que un visitante continúe con su recorrido.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) en un grupo de informes. En esta métrica se incluyen todos los tipos de vínculos, específicamente [Vínculos personalizados](../dimensions/custom-link.md), [Vínculos de descarga](../dimensions/download-link.md) y [Vínculos de salida](../dimensions/exit-link.md). No incluye llamadas de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar con métricas similares

* **Eventos de página vs. [Vistas de página](page-views.md)**: Los eventos de página cuentan el número de llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) y excluyen las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)). Las vistas de página son lo contrario; cuenta el número de llamadas de seguimiento de vista de página y excluye los vínculos.
