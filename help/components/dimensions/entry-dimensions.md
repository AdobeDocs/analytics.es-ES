---
title: Dimensiones de entrada
description: Incluye las dimensiones de entrada y su uso.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '234'
ht-degree: 100%

---


# Dimensiones de entrada

*Esta página de ayuda describe cómo funcionan las entradas como una dimensión. Para obtener información sobre cómo funcionan las entradas como métricas, consulte la métrica [Entradas](../metrics/entries.md).*

Las dimensiones de entrada se basan en visitas. Registran el primer elemento de dimensión y lo mantienen durante toda la visita. Las dimensiones de entrada están disponibles para todas las variables con las rutas habilitadas en [Variables de tráfico](/help/admin/admin/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

## Rellenar dimensiones de entrada con datos

Una dimensión de entrada determinada se basa en la variable de tráfico asociada. Si la variable que no es de entrada tiene datos, su dimensión de entrada asociada también contendrá datos. No se requieren cambios de implementación para las dimensiones de entrada si las variables de tráfico contienen datos.

## Elementos de dimensión

Dado que las variables de entrada generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de entrada determinada coinciden con los elementos de dimensión en su dimensión de no entrada asociada. Por ejemplo, los elementos de dimensión de la dimensión “Página de entrada” contienen elementos de dimensión similares en la dimensión “Página”.

## Página de entrada original

La dimensión “Página de entrada original” funciona de forma diferente que otras dimensiones de entrada. En lugar de preservar la página de entrada para una visita determinada, conserva la primera página de entrada durante toda la vida de la cookie de ese visitante. Por ejemplo, si aterriza en `https://example.com/page4` para la primera visita al sitio y un año después aterriza en `https://example.com/store`, la dimensión “Página de entrada original” incluye `https://example.com/page4` como elemento de dimensión.
