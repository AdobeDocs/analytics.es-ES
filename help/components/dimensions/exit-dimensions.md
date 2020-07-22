---
title: Dimensiones de salida
description: Las dimensiones de salida de Listas y su uso.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Dimensiones de salida

*Esta página de ayuda describe cómo funcionan las salidas como una dimensión. Para obtener información sobre cómo funcionan las salidas como métricas, consulte la métrica[Salidas](../metrics/exits.md).*

Las dimensiones de salida registran el último elemento de dimensión y lo aplican de forma retroactiva a todas las visitas individuales de la visita. Las dimensiones de salida están disponibles para todas las variables con las rutas habilitadas en Variables [de](/help/admin/admin/c-traffic-variables/traffic-var.md) tráfico en la configuración del grupo de informes.

## Rellenar dimensiones de salida con datos

Una dimensión de salida determinada se basa en la variable de tráfico asociada. Si la variable no de salida tiene datos, su dimensión de salida asociada también contiene datos. No se requieren cambios de implementación para las dimensiones de salida si las variables de tráfico contienen datos.

## Elementos de dimensión

Dado que las variables de salida generalmente se basan en cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión. Los valores de una dimensión de salida determinada coinciden con los elementos de dimensión en su dimensión de no salida asociada. Por ejemplo, los elementos de dimensión de la dimensión &#39;Página de salida&#39; contienen elementos de dimensión similares en la dimensión &#39;Página&#39;.
