---
title: Páginas no encontradas (métricas)
description: Número de visitas que contienen un error.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Páginas no encontradas

*En esta página de ayuda se describe cómo funciona &quot;Páginas no encontradas&quot; como métrica. Consulte la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md) para obtener más información.*

La métrica “Páginas no encontradas” muestra el número de visitas en las que la página contenía un error. Esta métrica es valiosa cuando desea ver qué páginas o direcciones URL contenían mensajes de error (como un 404), para que pueda determinar la causa del error y corregirlo.

* Cálculo de esta métrica[](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)
* Esta métrica cuenta todas las visitas en las que la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) es igual al valor de `"errorPage"`. Es el equivalente de métrica de la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md).](referrer.md)

## Populate this dimension with data

This dimension retrieves data from the [`pageType` and `g` query strings](/help/implement/validate/query-parameters.md) in image requests. If the `pageType` query string equals `errorPage`, the `g` query string (page URL) is recorded. AppMeasurement collects this data using the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. If the `pageType` variable is not defined or set to anything other than `errorPage`, no data for this dimension is collected.

## Dimension items

Dimension items include the URLs of pages on your site where an error occurred.
