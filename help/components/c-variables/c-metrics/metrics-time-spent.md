---
description: Adobe Analytics ofrece varias métricas y dimensiones de Tiempo empleado. Averigüe qué son y cómo se calculan.
solution: Analytics
title: Tiempo empleado
topic: Metrics
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Métricas de tiempo empleado

Adobe Analytics ofrece varias formas de determinar el tiempo empleado en los informes de Analytics. En la mayoría de los casos, el tiempo empleado se calcula siguiendo los pasos siguientes:

1. Para una visita individual determinada, observe la marca de tiempo y el valor de dimensión.
1. Compare esta visita con la marca de tiempo de la siguiente visita en la visita.
1. La cantidad de tiempo que transcurrió entre estas dos visitas individuales contribuye al tiempo empleado para ese valor de dimensión.

Al ver las métricas de tiempo empleado, tenga en cuenta lo siguiente:

* El tiempo empleado tiene en cuenta la asignación y la caducidad.
* Las vistas de página y los tipos de visitas de seguimiento de vínculos se tienen en cuenta al calcular el tiempo empleado en datos.
* El tiempo empleado no se mide durante la última visita individual de la visita, ya que no hay ninguna solicitud de imagen subsiguiente para medir el tiempo transcurrido.
* Las devoluciones no pueden medir el tiempo empleado, ya que la visita consiste en una sola visita.

## Segundos totales empleados

Cantidad total de tiempo que todos los visitantes interactuaron con un valor de dimensión, medido en segundos.

## Tiempo empleado por visita (segundos)

Cantidad promedio de tiempo que los visitantes interactúan con un valor de dimensión en una visita. Su cálculo aproximado es `Total seconds spent / (Visits - Bounces)`.

## Tiempo empleado por visitante (segundos)

Cantidad promedio de tiempo que los visitantes interactúan con un valor de dimensión durante toda la vida del visitante. Su cálculo aproximado es `Total seconds spent / (Unique Visitors - Bounces)`.

## Tiempo promedio empleado en el sitio (segundos)

Cantidad promedio de tiempo invertido en el sitio, generalmente asociado a una dimensión de fecha. Aunque esta métrica generalmente muestra las tendencias del tiempo empleado con el paso del tiempo, también puede utilizarse con dimensiones como cálculo alternativo al Tiempo empleado por visita. Su cálculo aproximado es `Total seconds spent / (Sequences - Bounces)`. Las secuencias son una serie de visitas individuales en las que el valor de la dimensión no ha cambiado.

> [!NOTE] El tiempo empleado por visita y el tiempo promedio empleado en el sitio son métricas similares. La diferencia entre estas dos métricas es su denominador; el tiempo empleado por visita utiliza `visits - bounces`, mientras que el tiempo promedio empleado en el sitio utiliza `sequences - bounces`. En el nivel de visita, estas métricas parecen similares, pero pueden tener algunas diferencias en el nivel de visita individual.

## Tiempo promedio empleado en la página

Solo está disponible en el Creador de informes. En la mayoría de los casos, utilice el tiempo empleado por visita en su lugar.
