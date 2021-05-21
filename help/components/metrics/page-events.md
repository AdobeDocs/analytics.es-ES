---
title: Eventos de página
description: Número de acciones de seguimiento de vínculos activadas.
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---

# Eventos de página

La métrica “Eventos de página” muestra la cantidad de veces que se realizó una llamada de seguimiento de vínculo. Esta métrica es útil cuando desea comprender qué páginas tienen el contenido más atractivo. La medición para esta métrica es muy valiosa cuando un visitante puede realizar una acción en la página sin navegar a una nueva página.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) en un grupo de informes. Se incluyen todos los tipos de vínculos (vínculos personalizados, vínculos de descarga y vínculos de salida). No incluye las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar con métricas similares

* **Eventos de página vs. [Vistas de página](page-views.md)**: Los eventos de página cuentan el número de llamadas de seguimiento de vínculos (`tl()`) y excluyen las llamadas de seguimiento de vista de páginas (`t()`). Vistas de página es lo contrario; cuenta el número de llamadas de seguimiento de vista de página y excluye los vínculos.
