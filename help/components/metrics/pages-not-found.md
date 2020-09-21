---
title: Páginas no encontradas
description: Número de visitas que contienen un error.
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---


# Páginas no encontradas

*En esta página de ayuda se describe cómo funciona &quot;Páginas no encontradas&quot; como métrica. Consulte la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md) para obtener más información.*

La métrica “Páginas no encontradas” muestra el número de visitas en las que la página contenía un error. Esta métrica es valiosa cuando desea ver qué páginas o direcciones URL contenían mensajes de error (como un 404), para que pueda determinar la causa del error y corregirlo.

## Cálculo de esta métrica

Esta métrica cuenta todas las visitas en las que la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md) es igual al valor de `"errorPage"`. Es el equivalente de métrica de la dimensión [Páginas no encontradas](../dimensions/pages-not-found.md).