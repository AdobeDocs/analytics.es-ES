---
description: Muestra la cantidad de tiempo que los visitantes emplearon en la página.
solution: Analytics
title: Tiempo invertido en la página
topic: Reports
translation-type: tm+mt
source-git-commit: df64b85f2567df68d2f710762596e4960214a4f6

---


# Time spent on page

Adobe Analytics ofrece varias formas de determinar el tiempo empleado en los informes de Analytics. En la mayoría de los casos, el tiempo empleado se calcula siguiendo los pasos siguientes:

1. Para una visita individual determinada, observe la marca de tiempo y el valor de dimensión.
2. Compare esta visita con la marca de tiempo de la siguiente visita en la visita.
3. La cantidad de tiempo que transcurrió entre estas dos visitas individuales contribuye al tiempo empleado para esa página.

Cuando visualice datos de dimensiones de tiempo empleado, tenga en cuenta lo siguiente:

* El tiempo empleado tiene en cuenta la asignación y la caducidad.
* Las vistas de página y los tipos de visitas de seguimiento de vínculos se tienen en cuenta al calcular el tiempo empleado en datos.
* El tiempo empleado no se mide durante la última visita individual de la visita, ya que no hay ninguna solicitud de imagen subsiguiente para medir el tiempo transcurrido.
* Las devoluciones no pueden medir el tiempo empleado, ya que la visita consiste en una sola visita.

El tiempo empleado en la página mide el tiempo transcurrido entre las visitas individuales de una visita. Existen dimensiones independientes entre **granular** y **agrupado**.

* **** Granular: Cada valor de dimensión es un número diferente de segundos transcurridos entre dos visitas.
* **** Agrupado: Cada valor de dimensión es un bloque predefinido:
   * Menos de 15 segundos
   * de 15 a 29 segundos
   * de 1 a 3 minutos
   * de 3 a 5 minutos
   * de 5 a 10 minutos
   * de 10 a 15 minutos
   * de 15 a 20 minutos
   * de 20 a 30 minutos
   * Más de 30 minutos

Esta dimensión se basa en visitas individuales, que si se utiliza como desglose pueden proporcionar datos más significativos. Compare esta dimensión con el [tiempo empleado por visita](reports-time-spent-per-visit.md), que es una dimensión basada en visitas.

![Tiempo empleado](/help/components/c-variables/c-metrics/assets/time-spent1.png)
