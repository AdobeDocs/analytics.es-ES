---
title: Compatibilidad con componentes en Data Warehouse
description: Descubra qué dimensiones y métricas están disponibles al crear una solicitud de Data Warehouse, cuáles no están disponibles y cuáles se comportan de forma diferente.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Compatibilidad con componentes en Data Warehouse

En esta página se describen las dimensiones y métricas que puede utilizar para crear una solicitud de Data Warehouse. Las secciones incluyen qué componentes están disponibles, cuáles no y cuáles se comportan de forma diferente que en otras herramientas de Adobe Analytics.

## Dimensiones exclusivas de Data Warehouse

Las siguientes dimensiones se pueden utilizar en Data Warehouse, pero no están disponibles en otras funciones de Adobe Analytics.

* [[!UICONTROL ID de visitante de Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL Dirección IP]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL URL de la página]](/help/components/dimensions/page-url.md)
* [[!UICONTROL ID de compra]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL ID de visitante]](/help/components/dimensions/visitor-id.md)

## Dimensiones no admitidas

Las siguientes dimensiones no están disponibles en los informes ni en los segmentos de Data Warehouse:

* [[!UICONTROL a. m./p. m.]](/help/components/dimensions/am-pm.md)
* Todas las dimensiones de entrada, excepto [[!UICONTROL Página de entrada]](/help/components/dimensions/entry-dimensions.md) y [[!UICONTROL Página de entrada original]](/help/components/dimensions/entry-dimensions.md), que están permitidas
* Todas las dimensiones de salida, excepto [[!UICONTROL Página de salida]](/help/components/dimensions/exit-dimensions.md) y [[!UICONTROL Vínculo de salida]](/help/components/dimensions/exit-link.md) que están permitidos
* [[!UICONTROL Profundidad de la visita]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL Frecuencia de retorno]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL Tiempo previo al evento]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL Tiempo empleado en la página - Agrupado]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL Tiempo empleado por visita - Agrupado]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL Clasificación de todas las páginas de búsqueda]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL Variables de jerarquía]](/help/components/dimensions/overview.md#retired-dimensions)
* [[!UICONTROL Tipo de visita]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL Búsqueda de pago]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL Visitas a una sola página]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL Motivo de exclusión de seguimiento]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL Estados de EE. UU.]](/help/components/dimensions/us-states.md)

Algunas dimensiones están disponibles en una solicitud de Data Warehouse, pero no se pueden usar dentro de un segmento. Consulte [Compatibilidad de segmentos de Data Warehouse](segment-compatibility.md) para obtener más información.

## Dimensiones con formato de fecha no estándar

Las siguientes dimensiones basadas en el tiempo son compatibles con los informes de Data Warehouse, pero su salida utiliza un formato no estándar:

* [[!UICONTROL Año]](/help/components/dimensions/year.md)
* [[!UICONTROL Trimestre]](/help/components/dimensions/quarter.md)
* [[!UICONTROL Mes]](/help/components/dimensions/month.md)
* [[!UICONTROL Semana]](/help/components/dimensions/week.md)
* [[!UICONTROL Día]](/help/components/dimensions/day.md)
* [[!UICONTROL Hora]](/help/components/dimensions/hour.md)
* [[!UICONTROL Minuto]](/help/components/dimensions/minute.md)

Los valores de fecha se muestran con el formato `1YYMMDDHHMM`:

* **Año (AA)**: Desplazamiento por 1900. Agregue `1900` a los tres primeros dígitos. Por ejemplo, `125` = año **2025**.
* **Mes**: basado en cero. Enero = `00`, febrero = `01`, ..., diciembre = `11`.

Por ejemplo, si el campo Intervalo de fechas de la semana muestra `1260901`, el año es 1900 + 126 = **2026** y el mes es 09 = **octubre**.

## Métricas definidas de forma diferente en Data Warehouse

* **[[!UICONTROL Visitas]](/help/components/metrics/visits.md)**: Excluye las visitas de cookies no persistentes, a diferencia de la métrica Visitas de otras herramientas de Adobe Analytics.
* **[[!UICONTROL Visitas - Todos los visitantes]](/help/components/metrics/visits.md)**: Cuenta todos los visitantes, incluidos los que tienen cookies no persistentes, por lo que es el equivalente más cercano a la métrica estándar [!UICONTROL Visitas] que se usa en otras partes de Adobe Analytics.

## Métricas no admitidas

Las siguientes métricas no están disponibles en Data Warehouse:

* [[!UICONTROL Devoluciones]](/help/components/metrics/bounces.md)
* [[!UICONTROL Entradas]](/help/components/metrics/entries.md)
* [[!UICONTROL Salidas]](/help/components/metrics/exits.md)
* [[!UICONTROL Recargas]](/help/components/metrics/reloads.md)
* [[!UICONTROL Acceso único]](/help/components/metrics/single-access.md)
* Cualquier métrica de [[!UICONTROL tiempo empleado]](/help/components/metrics/time-spent.md)
* Cualquier métrica que use un modelo de atribución [participación](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)
