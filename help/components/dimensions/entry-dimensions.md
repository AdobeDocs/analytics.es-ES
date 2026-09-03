---
title: Dimensiones de entrada
description: Incluye las dimensiones de entrada y su uso.
keywords: página de entrada, sección de entrada al sitio, servidor de entrada, conocimiento personalizado de entrada
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
TQID: https://experienceleague.adobe.com/6a6Xy8SEqjcnuB1Acbwkesw6OA7Nggld5ppWtjYaj5k
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 75%

---

# Dimensiones de entrada

*Esta página de ayuda describe cómo funcionan las entradas como una [dimensión](overview.md). Para obtener información sobre cómo funcionan las entradas como métricas, consulte la métrica [Entradas](../metrics/entries.md).*

Las dimensiones de entrada están [basadas en visitas](../metrics/visits.md). Registran el primer elemento de dimensión y lo mantienen durante toda la visita. Las dimensiones de entrada están disponibles para todas las variables con las rutas habilitadas en [Variables de tráfico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

>[!TIP]
>Si desea ver datos basados en la primera visita individual de una visita en lugar del primer valor visto en una visita, puede usar un [segmento](/help/components/segmentation/seg-overview.md). Use un contenedor de visita individual en el que [Profundidad de visita](hit-depth.md) sea igual a 1 y luego use ese segmento con la variable deseada.

## Rellenar dimensiones de entrada con datos

Una entrada determinada [dimension](overview.md) se basa en su variable de tráfico asociada. Si la variable que no es de entrada tiene datos, su dimensión de entrada asociada también contendrá datos. No se requieren cambios de implementación para las dimensiones de entrada si las variables de tráfico contienen datos.

## Elementos de dimensión

Dado que las variables de entrada generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de entrada determinada coinciden con los elementos de dimensión en su dimensión de no entrada asociada. Por ejemplo, los elementos de dimensión de la dimensión “Página de entrada” contienen elementos de dimensión similares en la dimensión “Página”.

## Página de entrada original

La dimensión “Página de entrada original” funciona de forma diferente que otras dimensiones de entrada. En lugar de preservar la página de entrada para una visita determinada, conserva la primera página de entrada durante toda la vida de la cookie de ese visitante. Por ejemplo, si aterriza en `https://example.com/page4` para la primera visita al sitio y un año después aterriza en `https://example.com/store`, la dimensión “Página de entrada original” incluye `https://example.com/page4` como elemento de dimensión.
