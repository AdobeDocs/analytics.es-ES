---
title: Dimensiones de entrada
description: Listas dimensiones de entrada y su uso.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Dimensiones de entrada

*Esta página de ayuda describe cómo funcionan las entradas como dimensiones. Para obtener información sobre cómo funcionan las entradas como métricas, consulte la métrica[Entradas](../metrics/entries.md).*

Las dimensiones de entrada se basan en visitas. Registran el primer valor de dimensión y lo mantienen durante toda la visita. Las dimensiones de entrada están disponibles para todas las variables con las rutas habilitadas en Variables [de](/help/admin/admin/c-traffic-variables/traffic-var.md) tráfico en la configuración del grupo de informes.

## Rellenar dimensiones de entrada con datos

Una dimensión de entrada determinada se basa en la variable de tráfico asociada. Si la variable que no es de entrada tiene datos, su dimensión de entrada asociada también contiene datos. No se requieren cambios de implementación para las dimensiones de entrada si las variables de tráfico contienen datos.

## Valores de dimensión

Dado que las variables de entrada generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los valores de dimensión. Los valores de una dimensión de entrada determinada coinciden con los valores de dimensión en su dimensión de no entrada asociada. Por ejemplo, los valores de dimensión de la dimensión &#39;Página de entrada&#39; contienen valores de dimensión similares en la dimensión &#39;Página&#39;.

## Página de entrada original

La dimensión &#39;Página de entrada original&#39; funciona de forma diferente que otras dimensiones de entrada. En lugar de preservar la página de entrada para una visita determinada, conserva la primera página de entrada durante toda la vida de la cookie de ese visitante. Por ejemplo, si aterriza `https://example.com/page4` para la primera visita al sitio, un año después aterriza `https://example.com/store`, la dimensión &#39;Página de entrada original&#39; se lista `https://example.com/page4` como valor de dimensión.
