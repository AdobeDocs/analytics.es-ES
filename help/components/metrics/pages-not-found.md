---
title: Páginas no encontradas (métricas)
description: Número de visitas que contienen un error.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 45%

---

# Páginas no encontradas

*En esta página de ayuda se describe cómo funciona &quot;Páginas no encontradas&quot; como métrica. Consulte la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md) para obtener más información.*

La [métrica](overview.md) &quot;Páginas no encontradas&quot; muestra el número de visitas configurado o en las que persiste una dimensión en el momento en que un visitante encontró un error. Esta métrica es valiosa cuando desea ver qué páginas o direcciones URL contenían mensajes de error (como un 404). A continuación, puede pasar esta información al equipo de desarrollo web, que puede determinar la causa del error y corregirlo.

## Cálculo de esta métrica

Esta métrica cuenta todas las visitas en las que la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) es igual al valor de `"errorPage"`. Es el equivalente de métrica de la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md).
