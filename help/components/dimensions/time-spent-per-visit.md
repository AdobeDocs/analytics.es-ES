---
title: Tiempo empleado por visita
description: Cantidad total de tiempo que duró la visita.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '302'
ht-degree: 100%

---


# Tiempo empleado por visita

*En esta página de ayuda se describe el funcionamiento de “Tiempo empleado por visita” como sus dimensiones correspondientes. Consulte la métrica [Tiempo empleado por visita](../metrics/time-spent-per-visit.md) para obtener más información.*

Las dimensiones “Tiempo empleado por visita” registran la cantidad de tiempo que un visitante ha invertido en toda la visita. Para medir el cálculo se utilizan los pasos siguientes:

1. Observe la marca de tiempo de la primera visita individual de la visita.
2. Compare esta visita individual con la marca de tiempo de la última de la visita general.
3. La cantidad de tiempo que transcurrió entre estas dos visitas individuales contribuye al tiempo invertido.

Estas dimensiones son valiosas cuando desea comprender cuánto tiempo interactúan los visitantes con el sitio en general.

>[!TIP]
>
>El tiempo empleado requiere al menos dos visitas individuales en una visita para medir el tiempo. Las visitas que consisten en una visita individual no aparecen en esta dimensión.

Esta dimensión se basa en visitas, lo que significa que el valor se aplica a cada visita individual dentro de la visita y no cambia. Compare esta dimensión con el [Tiempo empleado en la página](time-spent-on-page.md), que es una dimensión basada en visitas individuales.

Esta dimensión está relacionada con el [Tiempo promedio empleado en el sitio](../metrics/average-time-on-site.md) y con las métricas de [Tiempo empleado por visita](../metrics/time-spent-per-visit.md).

## Rellene esta dimensión con datos

Estas dimensiones funcionan de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, estas dimensiones funcionan.

## Elementos de dimensión

Hay varias dimensiones para el tiempo invertido por visita:

* **Tiempo empleado por visita (agrupado)**: La cantidad de tiempo se agrupa. Los elementos de dimensión varían de `"Less than 1 minute"` a `"More than 15 hours"`. Las visitas no suelen durar más de 12 horas; sin embargo, las visitas pueden superar las 12 horas si se utilizan visitas con marca de tiempo o fuentes de datos.
* **Tiempo empleado por visita (granular)**: Cada número de segundos es un elemento de dimensión único. Esta dimensión no está disponible en Reports &amp; Analytics ni en Data Warehouse.

Consulte [Información general sobre el tiempo empleado](../metrics/time-spent.md) para saber más detalles sobre el tiempo invertido.
