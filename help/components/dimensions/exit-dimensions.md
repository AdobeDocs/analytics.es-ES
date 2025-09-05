---
title: Dimensiones de salida
description: Las dimensiones de salida de Listas y su uso.
keywords: página de salida, sección del sitio de salida, servidor de salida, conocimiento personalizado de salida
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# Dimensiones de salida

*Esta página de ayuda describe cómo funcionan las salidas como una [dimensión](overview.md). Para obtener información sobre cómo funcionan las salidas como métricas, consulte la métrica [Salidas](../metrics/exits.md).*

Las dimensiones de salidas registran el último elemento de dimensión y lo aplican de forma retroactiva a todas las visitas individuales de la visita. Las dimensiones de salida están disponibles para todas las variables con las rutas habilitadas en [Variables de tráfico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

## Rellenar dimensiones de salida con datos

Una dimensión de salida determinada se basa en la variable de tráfico asociada. Si la variable que no es de salida tiene datos, su dimensión de salida asociada también contendrá datos. No se requieren cambios de implementación para las dimensiones de salida si las variables de tráfico contienen datos.

## Elementos de dimensión

Dado que las variables de salida generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de salida determinada coinciden con los elementos de la dimensión asociada que no sea de salida. Por ejemplo, los elementos de dimensión de la dimensión “Página de salida” contienen elementos de dimensión similares en la dimensión “Página”.
