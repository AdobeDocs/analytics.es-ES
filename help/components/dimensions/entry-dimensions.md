---
title: Dimensiones de entrada
description: Incluye las dimensiones de entrada y su uso.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# Dimensiones de entrada

*Esta página de ayuda describe cómo funcionan las entradas como una dimensión. Para obtener información sobre cómo funcionan las entradas como métricas, consulte la métrica[Entradas](../metrics/entries.md).*

Las dimensiones de entrada se basan en visitas. Registran el primer elemento de dimensión y lo mantienen durante toda la visita. Las dimensiones de entrada están disponibles para todas las variables con las rutas habilitadas en [Variables de tráfico](/help/admin/admin/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

## Rellenar dimensiones de entrada con datos

Una dimensión de entrada determinada se basa en la variable de tráfico asociada. Si la variable que no es de entrada tiene datos, su dimensión de entrada asociada también contendrá datos. No se requieren cambios de implementación para las dimensiones de entrada si las variables de tráfico contienen datos.

## Elementos de Dimension

Dado que las variables de entrada generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de entrada determinada coinciden con los elementos de dimensión en su dimensión de no entrada asociada. Por ejemplo, los elementos de dimensión de la dimensión &#39;Página de entrada&#39; contienen elementos de dimensión similares en la dimensión &#39;Página&#39;.

## Página de entrada original

La dimensión “Página de entrada original” funciona de forma diferente que otras dimensiones de entrada. En lugar de preservar la página de entrada para una visita determinada, conserva la primera página de entrada durante toda la vida de la cookie de ese visitante. For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
