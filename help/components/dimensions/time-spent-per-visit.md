---
title: Tiempo empleado por visita
description: Cantidad total de tiempo que tardó la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 11%

---


# Tiempo empleado por visita

*En esta página de ayuda se describe cómo funciona &#39;Tiempo empleado por visita&#39; como sus dimensiones respectivas. Consulte la métrica[Tiempo empleado por visita](../metrics/time-spent-per-visit.md)para obtener más información.*

Las dimensiones &#39;Tiempo empleado por visita&#39; registran la cantidad de tiempo que un visitante se emplea en toda la visita. Para medir el cálculo se utilizan los pasos siguientes:

1. Observe la marca de tiempo de la primera visita individual de la visita.
2. Compare esta visita individual con la marca de tiempo de la última de la visita general.
3. La cantidad de tiempo que transcurrió entre estas dos visitas contribuye al tiempo empleado.

Estas dimensiones son valiosas cuando desea comprender cuánto tiempo interactúan los visitantes con el sitio en general.

>[!TIP]
>
>El tiempo empleado requiere al menos dos visitas en una visita para medir el tiempo. Las visitas que consisten en una sola visita no aparecen en esta dimensión.

Esta dimensión se basa en visitas, lo que significa que el valor se aplica a cada visita individual dentro de la visita y no cambia. Compare esta dimensión con el [Tiempo empleado en la página](time-spent-on-page.md), que es una dimensión basada en visitas individuales.

Esta dimensión está relacionada con el tiempo [promedio invertido en el sitio](../metrics/average-time-on-site.md) y con las métricas de [tiempo empleado por visita](../metrics/time-spent-per-visit.md) .

## Rellenar esta dimensión con datos

Estas dimensiones funcionan de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, estas dimensiones funcionan.

## Elementos de dimensión

Existen varias dimensiones para el tiempo empleado por visita:

* **Tiempo empleado por visita - agrupado**: La cantidad de tiempo se agota. Los elementos de dimensión varían de `"Less than 1 minute"` a `"More than 15 hours"`. Las visitas no suelen durar más de 12 horas; sin embargo, las visitas pueden superar las 12 horas si se utilizan visitas con marca de hora o fuentes de datos.
* **Tiempo empleado por visita (granular**: Cada número de segundos es un elemento de dimensión único. Esta dimensión no está disponible en Informes y Analytics ni en Data warehouse.

Consulte [Información general](../metrics/time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.
