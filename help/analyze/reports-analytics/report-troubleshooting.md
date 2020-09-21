---
title: Prácticas recomendadas y resolución de problemas de la creación de informes
description: Prácticas recomendadas y sugerencias de resolución de problemas de la creación de informes.
keywords: best practices;failure;timeout;troubleshooting;slow
translation-type: ht
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: ht
source-wordcount: '567'
ht-degree: 100%

---


# Prácticas recomendadas y resolución de problemas de la creación de informes

*Esta página de ayuda se refiere a las prácticas recomendadas de Reports &amp; Analytics. Para obtener más información sobre Analysis Workspace, consulte [Optimización del rendimiento de Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md). Para Data Warehouse, consulte [Prácticas recomendadas sobre Data Warehouse](/help/export/data-warehouse/data-warehouse-bp.md).*

Adobe Analytics proporciona una interfaz de informes flexible que le permite generar una variedad de informes complejos. Mientras que la mayoría de los informes se generan muy rápidamente, puede encontrar informes que agoten el tiempo de espera o no se generen correctamente. Esta página explica los factores que afectan a la velocidad de generación de informes. Comprender esta información es útil para estructurar informes para que se generen correctamente.

## Tiempos de espera de informe y cola de solicitud

* **Tiempos de espera:** Un solo informe se desglosa en varias solicitudes (una por desglose), y cada solicitud está sujeta a un tiempo de espera individual. Los informes programados garantizan períodos de tiempo de ejecución más largos y es más fácil que sean satisfactorios que los informes que se generan directamente en una interfaz de usuario.
* **Cola del grupo de informes**: Cada grupo de informes mantiene una cola separada de solicitudes. Si se solicitan varios informes de forma simultánea, incluso de usuarios separados, un pequeño número de informes se genera simultáneamente. A medida que se completan los informes, los informes restantes se generan en el mismo orden en que se recibieron. Como resultado, si un gran número de informes complejos ya se encuentran en la cola del grupo de informes, puede que se agote el tiempo de ejecución de un informe que normalmente se genera rápidamente.

## Factores que afectan a la velocidad del informe

Los siguientes factores contribuyen a que los tiempos de generación de informes sean más largos. El aumento de uno de estos factores no suele afectar al rendimiento, pero puede retrasar otros informes en la cola del grupo de informes y provocar que se agote el tiempo de espera de un informe posterior.

* **Intervalo de tiempo del informe**: El factor más grande que afecta al tiempo de generación de informes es el número de meses solicitado. Si se reduce el número de meses de tres a uno también se reduce significativamente el tiempo de generación, pero si se reduce el intervalo de tiempo de un mes a una semana no tiene un gran impacto en el tiempo de generación de informes.
* **Número de métricas**: A medida que aumenta el número de métricas, aumenta el tiempo de ejecución del informe. A menudo, si se eliminan métricas, mejora el tiempo de generación de informes.
* **Número de desgloses**: Dentro de un informe, cada desglose representa una solicitud separada. Mientras que las solicitudes individuales se completan rápidamente, ejecutar cientos de desgloses en un solo informe puede ralentizar significativamente el tiempo de generación del informe y afectar a la cola de generación de informes.
* **Complejidad de segmento**: Los segmentos que consideran muchas dimensiones o tienen muchas reglas (24+) aumentan el impacto de procesamiento y el tiempo de generación del informe.
* **Número de valores únicos**: Los informes que contienen cientos de miles de valores únicos se generan más lentamente que los informes que contienen menos valores únicos, aunque el segmento o el filtro reduzcan el número de valores que finalmente aparecen en un informe. Por ejemplo, un informe que muestra términos de búsqueda normalmente se genera más lentamente que otros informes, incluso si se aplica un filtro para mostrar solo términos de búsqueda que contienen un valor específico.

## Otras opciones de creación de informes

Las siguientes directrices ayudan a aumentar la fiabilidad del envío de informes:

* Use el Data Warehouse para solicitar informes que contienen muchos desgloses o métricas. El Data Warehouse está diseñado para generar estos tipos de informes.
* Programar informes para que se ejecuten durante las horas de menor actividad. Esto aumenta la probabilidad de que un informe se devuelva porque la cola de solicitudes de un grupo de informes probablemente estará vacía durante estos tiempos.
* El Report Builder se puede utilizar para desglosar informes en intervalos de tiempo más breves y solicitudes que contengan menos métricas. A continuación, puede usar la funcionalidad de Excel nativo para fusionar datos de varias solicitudes en un único informe.
