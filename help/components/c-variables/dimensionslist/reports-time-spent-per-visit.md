---
description: 'null'
solution: Analytics
title: Tiempo empleado por visita
topic: Informes
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 77eac41cdcfe0ad71ffe81525f6de4dc6b2b48d4

---


# Tiempo empleado por visita

Adobe Analytics ofrece varias formas de determinar el tiempo empleado en los informes de Analytics. En la mayoría de los casos, el tiempo empleado se calcula siguiendo los pasos siguientes:

1. Para una visita determinada, observe la marca de tiempo de la primera visita.
2. Compare esta visita con la marca de tiempo de la última visita individual de la visita.
3. La cantidad de tiempo que transcurrió entre estas dos visitas determina la cantidad de tiempo empleado para esa visita.

Cuando visualice datos de dimensiones de tiempo empleado, tenga en cuenta lo siguiente:

* Las vistas de página y los tipos de visitas de seguimiento de vínculos se tienen en cuenta al calcular el tiempo empleado en datos.
* El tiempo empleado no se mide durante la última visita individual de la visita, ya que no hay ninguna solicitud de imagen posterior para medir el tiempo transcurrido.
* Las devoluciones no pueden medir el tiempo empleado, ya que la visita consiste en una sola visita.

El tiempo empleado por visita mide el tiempo total transcurrido en una visita. Existen dimensiones independientes entre **granular** y **agrupado**.

* **** Granular: Cada valor de dimensión es un número diferente de segundos que forman una visita.
* **** Agrupado: Cada valor de dimensión es un bloque predefinido:
   * Menos de 1 minuto
   * 1 a 5 minutos
   * 5 a 10 minutos
   * 30 a 60 minutos
   * 1 a 2 horas
   * 2 a 5 horas
   * 5 a 10 horas
   * 10 a 15 horas
   * Más de 15 horas

> [!NOTE] Las [visitas](../c-metrics/metrics-visit.md) suelen finalizar después de 12 horas de actividad. Sin embargo, las visitas pueden superar las 12 horas si se utilizan visitas con marca de hora o fuentes de datos.

Esta dimensión se basa en visitas. Compare esta dimensión con el [tiempo empleado en la página](reports-time-spent-on-page.md), que es una dimensión basada en visitas individuales.
