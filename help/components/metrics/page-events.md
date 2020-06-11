---
title: eventos de página
description: Número de acciones de seguimiento de vínculos activadas.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# eventos de página

La métrica &#39;eventos de página muestra la cantidad de veces que se realizó una llamada de seguimiento de vínculo. Esta métrica es útil cuando desea comprender qué páginas tienen el contenido más atractivo. La medición para esta métrica es muy valiosa cuando un visitante puede realizar una acción en la página sin navegar a una nueva página.

## Cómo se calcula esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) en un grupo de informes. Se incluyen todos los tipos de vínculos (vínculos personalizados, vínculos de descarga y vínculos de salida). No incluye las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar con métricas similares

* **eventos de página vs. vistas[](page-views.md)**de página: Los eventos de página cuentan el número de llamadas de seguimiento de vínculos (`tl()`) y excluyen las llamadas de seguimiento de vista de páginas (`t()`). vistas de página es lo contrario; cuenta el número de llamadas de seguimiento de vista de página y excluye los vínculos.
