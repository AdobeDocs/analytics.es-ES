---
description: 'null'
title: Tiempo empleado por visita
topic: Reports
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tiempo empleado por visita

Adobe Analytics ofrece varias formas de determinar el tiempo empleado en los informes de Analytics. En la mayoría de los casos, el tiempo empleado se calcula siguiendo los pasos siguientes:

1. Para una visita determinada, observe la marca de tiempo de la primera visita individual.
2. Compare esta visita individual con la marca de tiempo de la última de la visita general.
3. La cantidad de tiempo que transcurrió entre estas dos visitas individuales determina la cantidad de tiempo empleado para esa visita general.

Cuando visualice datos de dimensiones de tiempo empleado, tenga en cuenta lo siguiente:

* Las vistas de página y los tipos de visitas individuales de seguimiento de vínculos se tienen en cuenta al calcular el tiempo empleado en datos.
* El tiempo empleado no se mide durante la última visita individual de la visita general, ya que no hay ninguna solicitud de imagen posterior para medir el tiempo transcurrido.
* Las devoluciones no pueden medir el tiempo empleado, ya que la visita general consiste en una sola visita individual.

El tiempo empleado por visita mide el tiempo total transcurrido en una visita. Existen dimensiones independientes entre **granular** y **agrupado**.

* **Granular:** Cada valor de dimensión es un número diferente de segundos que forman una visita.
* **Agrupado:** Cada valor de dimensión es un grupo predefinido:
   * Menos de 1 minuto
   * 1 a 5 minutos
   * 5 a 10 minutos
   * 30 a 60 minutos
   * 1 a 2 horas
   * 2 a 5 horas
   * 5 a 10 horas
   * 10 a 15 horas
   * Más de 15 horas

> [!NOTE] [Visitas](../c-metrics/metrics-visit.md) suelen finalizar después de 12 horas de actividad. Sin embargo, las visitas pueden superar las 12 horas si se utilizan visitas individuales con marca de hora o fuentes de datos.

Esta dimensión se basa en visitas. Compare esta dimensión con el [Tiempo empleado en la página](reports-time-spent-on-page.md), que es una dimensión basada en visitas individuales.
