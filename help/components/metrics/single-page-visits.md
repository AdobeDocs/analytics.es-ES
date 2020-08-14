---
title: Visitas de página única
description: El número de veces que el elemento de dimensión 'Página' no cambió en una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# Visitas de página única

*En esta página de ayuda se describe cómo funciona “Visitas de página única” como métrica. Consulte la dimensión[Visitas de página única](../dimensions/single-page-visits.md)para obtener más información.*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. Esta métrica es útil en el contexto de dimensiones en las que desea ver visitas cortas, pero no tiene reglas tan estrictas como [Devoluciones](bounces.md).

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde el elemento de dimensión &#39;Página&#39; contenía solamente un valor único para toda la visita. Si un visitante vuelve a cargar la página o activa las llamadas de seguimiento de vínculos, aún se cuenta como una sola visita a la página. Tan pronto como la dimensión Página cambie a un segundo valor único, la visita ya no se califica como una visita de página única.

Consulte [Acceso único](single-access.md) para ver una comparación entre métricas.
