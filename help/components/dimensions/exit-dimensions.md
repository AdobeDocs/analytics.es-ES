---
title: Dimensiones de salida
description: Las dimensiones de salida de Listas y su uso.
keywords: página de salida, sección del sitio de salida, servidor de salida, conocimiento personalizado de salida
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 175
ht-degree: 94%

---

# Dimensiones de salida

*Esta página de ayuda describe cómo funcionan las salidas como una [dimensión](overview.md). Para obtener información sobre cómo funcionan las salidas como métricas, consulte la métrica [Salidas](../metrics/exits.md).*

Las dimensiones de salidas registran el último elemento de dimensión y lo aplican de forma retroactiva a todas las visitas individuales de la visita. Las dimensiones de salida están disponibles para todas las variables con las rutas habilitadas en [Variables de tráfico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

## Rellenar dimensiones de salida con datos

Una dimensión de salida determinada se basa en la variable de tráfico asociada. Si la variable que no es de salida tiene datos, su dimensión de salida asociada también contendrá datos. No se requieren cambios de implementación para las dimensiones de salida si las variables de tráfico contienen datos.

## Elementos de dimensión

Dado que las variables de salida generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de salida determinada coinciden con los elementos de la dimensión asociada que no sea de salida. Por ejemplo, los elementos de dimensión de la dimensión “Página de salida” contienen elementos de dimensión similares en la dimensión “Página”.
