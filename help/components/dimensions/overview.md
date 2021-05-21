---
title: Información general de dimensiones
description: Variables que contienen valores de cadena.
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '108'
ht-degree: 100%

---

# Información general de dimensiones

Las dimensiones son variables en Adobe Analytics que generalmente contienen valores de cadena. Las dimensiones comunes incluyen [Página](page.md), [Dominio de referencia](referring-domain.md) o una [eVar](evar.md). Por el contrario, las [métricas](../metrics/overview.md) contienen valores numéricos que se vinculan a una dimensión. Un informe básico muestra filas de valores de cadena (dimensión) frente a una columna de valores numéricos (métrica).

Por ejemplo, si combina la dimensión “Página” con la métrica “Visitas”, obtendrá un informe de clasificación que muestre las páginas más visitadas:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Cada dimensión representa una parte o faceta diferente del sitio. Puede combinar una o más de estas dimensiones con una o más métricas para crear un informe deseado.
