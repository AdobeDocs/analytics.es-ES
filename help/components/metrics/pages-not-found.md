---
title: Páginas no encontradas (métricas)
description: Número de visitas que contienen un error.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 96%

---

# Páginas no encontradas

*En esta página de ayuda se describe cómo funciona &quot;Páginas no encontradas&quot; como métrica. Consulte la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md) para obtener más información.*

La métrica “Páginas no encontradas” muestra el número de visitas en las que la página contenía un error. Esta métrica es valiosa cuando desea ver qué páginas o direcciones URL contenían mensajes de error (como un 404), para que pueda determinar la causa del error y corregirlo.

## Cálculo de esta métrica

Esta métrica cuenta todas las visitas en las que la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) es igual al valor de `"errorPage"`. Es el equivalente de métrica de la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md).
