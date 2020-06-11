---
title: Visitas a una sola página
description: El número de veces que el valor de dimensión 'Página' no ha cambiado en una visita.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Visitas a una sola página

*En esta página de ayuda se describe cómo funciona &quot;Visitas a una sola página&quot; como métrica. Consulte la dimensión[Visitas](../dimensions/single-page-visits.md)a una sola página para obtener más información.*

La métrica &#39;Visitas a una sola página&#39; muestra el número de visitas donde el valor de la dimensión [Página](../dimensions/page.md) sólo contenía un valor único para toda la visita. Esta métrica es útil en el contexto de dimensiones en las que desea ver visitas cortas, pero no tiene reglas tan estrictas como [Devoluciones](bounces.md).

## Cómo se calcula esta métrica

Esta métrica cuenta el número de visitas en las que el valor de dimensión &#39;Página&#39; solo contenía un valor único para toda la visita. Si un visitante vuelve a cargar la página o activa las llamadas de seguimiento de vínculos, aún se cuenta como una sola visita a la página. Tan pronto como la dimensión Página cambia a un segundo valor único, la visita ya no se califica como una visita a una sola página.

Consulte Acceso [](single-access.md) único para ver una comparación entre métricas.
