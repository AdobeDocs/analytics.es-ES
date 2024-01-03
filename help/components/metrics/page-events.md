---
title: Eventos de página
description: Número de acciones de seguimiento de vínculos activadas.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: a7434f72159a575f9ad7bf29644cb17777382df7
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 40%

---

# Eventos de página

Los &quot;Eventos de página&quot; [métrica](overview.md) muestra la cantidad de veces que se realizó una llamada de seguimiento de vínculos. Esta métrica es útil cuando desea comprender qué páginas tienen el contenido más atractivo. La medición para esta métrica es muy valiosa cuando un visitante puede realizar una acción en la página sin navegar a una nueva página.

## Cálculo de esta métrica

Esta métrica cuenta todos [Llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) en un grupo de informes. Todos los tipos de vínculos se incluyen en esta métrica, específicamente [Vínculos personalizados](../dimensions/custom-link.md), [Vínculos de descarga](../dimensions/download-link.md), y [Vínculos de salida](../dimensions/exit-link.md). No incluye [Llamadas de seguimiento de vista de página (`t()`)](/help/implement/vars/functions/t-method.md).

## Comparar con métricas similares

* **Eventos de página vs. [Page views](page-views.md)**: Los eventos de página cuentan el número de llamadas de seguimiento de vínculos (`tl()`) y excluyen las llamadas de seguimiento de vista de página (`t()`). Las vistas de página son lo contrario; cuenta el número de llamadas de seguimiento de vista de página y excluye los vínculos.
