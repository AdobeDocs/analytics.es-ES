---
description: Adobe Analytics proporciona una interfaz de sistema de informes flexible que le permite generar una gran variedad de informes complejos. Aunque la mayoría de los informes se generan muy rápidamente, es posible que encuentre informes que agoten el tiempo de espera o que no se generen correctamente. Para ayudar a evitar errores en la generación de informes, esta sección explica muchos factores que afectan la velocidad de generación de informes. El comprender esta información puede ayudarle a estructurar los informes para que tengan más posibilidades de generarlos correctamente.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Información sobre prácticas recomendadas y resolución de problemas
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Información sobre prácticas recomendadas y resolución de problemas

Adobe Analytics proporciona una interfaz de sistema de informes flexible que le permite generar una gran variedad de informes complejos. Aunque la mayoría de los informes se generan muy rápidamente, es posible que encuentre informes que agoten el tiempo de espera o que no se generen correctamente. Para ayudar a evitar errores en la generación de informes, esta sección explica muchos factores que afectan la velocidad de generación de informes. El comprender esta información puede ayudarle a estructurar los informes para que tengan más posibilidades de generarlos correctamente.

>[!Note]
>Estas recomendaciones se aplican a Reports &amp; Analytics, Ad Hoc Analysis y Report Builder.
>No se aplican a Analysis Workspace, que tiene su propio conjunto de [recomendaciones](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). Tampoco se aplican a [las recomendaciones](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html) de Data Warehouse. Un conjunto adicional de
>[recomendaciones](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) está disponibles para la API de informes de Adobe Analytics.

## Tiempos de espera de informe y cola de solicitud {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Tiempos de espera**

Un solo informe se divide en varias solicitudes (una por desglose) y cada solicitud está sujeta a un tiempo de espera individual. Los informes programados tienen períodos de tiempo de espera más largos y es más probable que tengan éxito que los informes que se generan directamente en una interfaz de usuario.

**Cola de grupos de informes**

Cada grupo de informes mantiene una cola de solicitudes por separado. Si se solicitan muchos informes simultáneamente, incluso de usuarios separados, se genera un pequeño número de informes simultáneamente. A medida que se completan los informes, los informes restantes se generan en el orden en que se recibieron. Como resultado, si ya hay una gran cantidad de informes complejos en la cola del grupo de informes, un informe que normalmente se genera rápidamente podría agotarse.

## Factores que afectan a la velocidad del informe  {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Los siguientes factores contribuyen a que los tiempos de generación de informes sean más largos. Si se aumenta uno de estos factores, es posible que no se agote el tiempo de espera para ese informe, pero puede que se retrase el resto de informes de la cola del grupo de informes y se agote el tiempo de espera de un informe posterior.

**Intervalo de tiempo del informe**

El factor más importante que afecta al tiempo de generación de informes es el número de meses solicitados. La reducción del número de meses de tres a uno disminuye significativamente el tiempo de generación, pero la reducción del intervalo de tiempo de un mes a una semana no tiene un gran impacto en el tiempo de generación de informes.

**Número de métricas**

A medida que aumenta el número de métricas, aumenta el tiempo de ejecución del informe. La eliminación de métricas a menudo mejora el tiempo de generación de informes.

**Número de desgloses**

Dentro de un informe, cada desglose representa una solicitud separada. Aunque las solicitudes individuales pueden completarse rápidamente, la ejecución de miles de desgloses en un solo informe puede ralentizar significativamente el tiempo de generación de informes y afectar a la cola del grupo de informes.

**Complejidad de segmentos**

Los segmentos que tienen en cuenta muchas dimensiones o muchas reglas (más de 24) aumentan el impacto del procesamiento y el tiempo de generación del informe.

**Número de valores únicos**

Los informes que contienen cientos de miles de valores únicos se generan más lentamente que los informes que contienen menos valores únicos, incluso si el segmento o filtro reduce el número de valores que finalmente aparecen en un informe. Por ejemplo: un informe que muestra términos de búsqueda generalmente se genera más lentamente que otros informes, incluso si se aplica un filtro para mostrar solamente los términos de búsqueda que contienen un valor específico.

## Otras opciones de informes  {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Además de reducir el intervalo de tiempo, el número de métricas y el número de desgloses de un informe, las siguientes directrices ayudan a aumentar la fiabilidad de envío del informe:

* Utilice el almacén de datos para solicitar informes que contengan muchos desgloses o métricas. El almacén de datos está diseñado para generar estos tipos de informes.
* Programar informes para que se ejecuten durante las horas no pico. Esto aumenta la probabilidad de que un informe se devuelva porque es más probable que la cola de solicitudes de un grupo de informes esté vacía durante esos tiempos.
* El Creador de informes se puede utilizar para desglosar informes en intervalos de tiempo más pequeños y solicitudes que contengan menos métricas. A continuación, puede utilizar la funcionalidad nativa de Excel para combinar datos de varias solicitudes en un solo informe.

