---
description: Adobe Analytics proporciona una interfaz de informes flexible que le permite generar una variedad de informes complejos. Mientras que la mayoría de los informes se generan muy rápidamente, puede encontrar informes que agoten el tiempo de espera o no se generen correctamente. Con el fin de ayudar a evitar fallos en la generación de informes, en esta sección se describen varios factores que tienen impacto en la velocidad de la generación de informes. Si se comprende esta información es útil para estructurar informes para que se generen correctamente.
keywords: prácticas recomendadas;error;tiempo de espera;resolución de problemas;lento
seo-description: Adobe Analytics proporciona una interfaz de informes flexible que le permite generar una variedad de informes complejos. Mientras que la mayoría de los informes se generan muy rápidamente, puede encontrar informes que agoten el tiempo de espera o no se generen correctamente. Con el fin de ayudar a evitar fallos en la generación de informes, en esta sección se describen varios factores que tienen impacto en la velocidad de la generación de informes. Si se comprende esta información es útil para estructurar informes para que se generen correctamente.
seo-title: Información sobre prácticas recomendadas y resolución de problemas
solution: Analytics
title: Información sobre prácticas recomendadas y resolución de problemas
topic: Informes
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Información sobre prácticas recomendadas y resolución de problemas

Adobe Analytics proporciona una interfaz de informes flexible que le permite generar una variedad de informes complejos. Mientras que la mayoría de los informes se generan muy rápidamente, puede encontrar informes que agoten el tiempo de espera o no se generen correctamente. Con el fin de ayudar a evitar fallos en la generación de informes, en esta sección se describen varios factores que tienen impacto en la velocidad de la generación de informes. Si se comprende esta información es útil para estructurar informes para que se generen correctamente.

>[!Note]
>Estas recomendaciones se aplican a Informes y análisis, Análisis específicos y Creador de informes.
>No se aplican a Analysis Workspace, que tiene su propio conjunto de [optimizaciones](/help/analyze/analysis-workspace/optimizing-performance.md). They also do not &gt;apply to Data Warehouse [best practices](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html). Un conjunto adicional de
>[las prácticas](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) recomendadas están disponibles para la API de informes de Adobe Analytics.

## Tiempos de espera de informe y cola de solicitud {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Tiempos de espera**

Un solo informe se rompe en varias solicitudes (una por desglose), y cada solicitud está sujeta a un tiempo de espera individual. Los informes programados garantizan períodos de tiempo de ejecución más largos y es más fácil que sean satisfactorios que los informes que se generan directamente en una interfaz de usuario.

**Cola del grupo de informes**

Cada grupo de informes mantiene una cola separada de solicitudes. Si se solicitan varios informes de forma simultánea, incluso de usuarios separados, un pequeño número de informes se genera simultáneamente. A medida que se completan los informes, los informes restantes se generan en el mismo orden en que se recibieron. Como resultado, si un gran número de informes complejos ya se encuentran en la cola del grupo de informes, puede que se agote el tiempo de ejecución de un informe que normalmente se genera rápidamente.

## Factores que afectan a la velocidad del informe {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Los siguientes factores contribuyen a que los tiempos de generación de informes sean más largos. Si se aumenta uno de estos factores puede no resultar en el agotamiento del tiempo de ejecución para el informe, pero puede retrasar otros informes de la cola del grupo de informes y provocar que el informe subsiguiente agote el tiempo de ejecución.

**Intervalo de tiempo de informe**

El factor más grande que afecta al tiempo de generación de informes es el número de meses solicitado. Si se reduce el número de meses de tres a uno también se reduce significativamente el tiempo de generación, pero si se reduce el intervalo de tiempo de un mes a una semana no tiene un gran impacto en el tiempo de generación de informes.

**Número de métricas**

A medida que aumenta el número de métricas, aumenta el tiempo de ejecución del informe. A menudo, si se eliminan métricas, mejora el tiempo de generación de informes.

**Número de desgloses**

Dentro de un informe, cada desglose representa una solicitud separada. Mientras que las solicitudes individuales se completan rápidamente, ejecutar cientos de desgloses en un solo informe puede ralentizar significativamente el tiempo de generación del informe y afectar a la cola de generación de informes.

**Complejidad de segmento**

Los segmentos que consideran muchas dimensiones o tienen muchas reglas (24+) aumentan el impacto de procesamiento y el tiempo de generación del informe.

**Número de valores únicos**

Los informes que contienen cientos de miles de valores únicos se generan más lentamente que los informes que contienen menos valores únicos, aunque el segmento o el filtro reduzcan el número de valores que finalmente aparecen en un informe. Por ejemplo, un informe que muestra términos de búsqueda normalmente se genera más lentamente que otros informes, incluso si se aplica un filtro para mostrar solo términos de búsqueda que contienen un valor específico.

## Otras opciones de informes {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Además de reducir el intervalo de tiempo, el número de métricas y el número de desgloses de un informe, las siguientes directrices ayudan a aumentar la fiabilidad de envío del informe:

* Use el Data Warehouse para solicitar informes que contienen muchos desgloses o métricas. El Data Warehouse está diseñado para generar estos tipos de informes.
* Programar informes para que se ejecuten durante las horas de menor actividad. Esto aumenta la probabilidad de que un informe se devuelva porque la cola de solicitudes de un grupo de informes probablemente estará vacía durante estos tiempos.
* El Report Builder se puede utilizar para desglosar informes en intervalos de tiempo más breves y solicitudes que contengan menos métricas. A continuación, puede usar la funcionalidad de Excel nativo para fusionar datos de varias solicitudes en un único informe.

