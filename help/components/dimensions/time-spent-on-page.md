---
title: Tiempo invertido en la página
description: Cantidad de tiempo que un visitante emplea en la página.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 13%

---


# Tiempo invertido en la página

La dimensión &#39;Tiempo empleado en la página&#39; registra la cantidad de tiempo que un visitante ha invertido en la página. Para medir el cálculo se utilizan los pasos siguientes:

1. Para una visita determinada, observe la marca de tiempo.
2. Compare esta visita individual con la marca de tiempo de la siguiente en la visita general. Tanto las visitas individuales de seguimiento de vista de página como las de seguimiento de vínculos cuentan.
3. La cantidad de tiempo que transcurrió entre estas dos visitas contribuye al tiempo empleado.

Esta dimensión es valiosa cuando desea comprender cuánto tiempo interactúan los visitantes con una métrica determinada del sitio.

>[!TIP]
>
>El tiempo empleado no se mide para la última visita individual de la visita, ya que no hay solicitudes de imagen subsiguientes para medir el tiempo transcurrido. Este concepto también se aplica a las visitas que consisten en una sola visita (una devolución).

Esta dimensión se basa en visitas individuales, lo que significa que el valor es diferente para cada visita. Compare esta dimensión con el [Tiempo empleado por visita](time-spent-per-visit.md), que es una dimensión basada en visitas. Un tiempo empleado mayor significa que un visitante permaneció más tiempo en una página (visita individual).

![Tiempo invertido en la página](../metrics/assets/time-spent2.png)

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Valores de dimensión

Existen varias dimensiones para el tiempo empleado en la página:

* **Tiempo empleado en la página - agrupado**: La cantidad de tiempo se agota. Los valores de dimensión varían de `"Less than 15 seconds"` a `"More than 30 minutes"`. El tiempo entre vistas de página no suele durar más de 30 minutos; sin embargo, el tiempo entre vistas de página puede superar los 30 minutos si se utilizan visitas con marca de hora o fuentes de datos.
* **Tiempo empleado en la página: granular**: Cada número de segundos es un valor de dimensión único.

Consulte [Información general](../metrics/time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.
