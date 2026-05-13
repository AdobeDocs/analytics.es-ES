---
title: Tiempo empleado por visita (dimensiones)
description: Cantidad total de tiempo que duró la visita.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 91%

---

# Tiempo empleado por visita

*Esta página de ayuda describe cómo funciona &#39;Tiempo empleado por visita&#39; como sus [dimensiones](overview.md) respectivas. Consulte la métrica [Tiempo empleado por visita](../metrics/time-spent-per-visit.md) para obtener más información.*

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
* **Tiempo empleado por visita (granular)**: Cada número de segundos es un elemento de dimensión único. Esta dimensión no está disponible en Data Warehouse.

Consulte [Información general sobre el tiempo empleado](../metrics/time-spent.md) para saber más detalles sobre el tiempo invertido.
