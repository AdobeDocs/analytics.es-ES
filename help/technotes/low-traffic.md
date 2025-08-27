---
description: Cuando un informe tiene muchos valores únicos, Adobe utiliza el elemento de dimensión Poco tráfico para mejorar el rendimiento del informe.
title: Valor de poco tráfico en Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 42d044c3c56f13a232b721ef60f64bcf622ffa9f
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 8%

---

# Valor de [!UICONTROL poco tráfico] en Adobe Analytics

Cuando una dimensión contiene millones de valores únicos, Adobe proporciona una funcionalidad para garantizar que los valores más importantes aparezcan en el informe de manera oportuna. Los valores únicos recopilados más allá de un determinado umbral se enumeran en un elemento de dimensión etiquetado como **[!UICONTROL Poco tráfico]**.

El elemento de dimensión [!UICONTROL Poco tráfico] permite a Adobe asegurarse de que los informes se devuelvan a tiempo tomando valores únicos excesivos y agrupándolos.

Tenga en cuenta que la lógica de [!UICONTROL poco tráfico] funciona mejor con dimensiones que tienen elementos que se repiten muchas veces durante el mes. Si los elementos de dimensión son casi o totalmente únicos en cada visita, el número de valores únicos alcanza el umbral rápidamente y todos los valores subsiguientes del mes terminan en el bloque [!UICONTROL Poco tráfico].

## Cómo ingresan los valores [!UICONTROL Poco tráfico]

De manera predeterminada, se establece un umbral de **2.000.000 de valores únicos** por dimensión, por grupo de informes y por mes calendario. Los elementos de Dimension que excedan este umbral de valor único se agrupan en [!UICONTROL Poco tráfico].

* Los elementos de Dimension recopilados antes de alcanzar el umbral se calculan de forma normal.
* Los elementos de Dimension recopilados después de superar el umbral se agrupan en [!UICONTROL Poco tráfico].

>[!NOTE]
>La dimensión [Página](../components/dimensions/page.md) usa varias columnas de back-end que se contabilizan todas en el umbral único, incluidas `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` y `click_context`. Estas columnas back-end pueden hacer que la lógica [!UICONTROL Poco tráfico] se aplique mucho antes de que el número de elementos de dimensión de página únicos en Workspace alcance el umbral.

El límite único de 2 000 000 se puede cambiar por dimensión. Consulte [Cambio de los umbrales de límite únicos](#changing-unique-limit-thresholds) a continuación. Al final de un mes natural, el número de valores únicos rastreados se restablece globalmente.

## Cómo los valores pueden escapar de [!UICONTROL Poco tráfico] después de superar el umbral

Si una dimensión determinada recopila más de 2 000 000 de valores únicos en un mes determinado, los elementos de dimensión individuales pueden volver a la creación de informes como elemento de dimensión propio. El caso de uso principal de esta función es permitir la creación de informes de elementos de dimensión cruciales que podrían recibir un aumento de popularidad a finales del mes siguiente a la superación del umbral único. Por ejemplo, si su organización ejecuta un sitio con millones de artículos y un nuevo artículo se vuelve popular hacia finales de mes, aún puede analizar el rendimiento de ese artículo. Esta lógica no pretende desagrupar todo lo que obtiene un determinado número de instancias, sino ofrecer una vía para analizar el contenido que recibe una afluencia de tráfico.

Los requisitos para que un elemento de dimensión individual salga de [!UICONTROL Poco tráfico] dependen de muchos factores, muchos de los cuales impiden que se pueda calcular un umbral exacto:

* **Número de servidores que procesan datos para el grupo de informes**: Los grupos de informes con más tráfico requieren más instancias de un solo elemento de dimensión para escapar de [!UICONTROL Poco tráfico].
* **Cantidad de tiempo entre cada instancia de elemento de dimensión**: Las visitas que contienen un elemento de dimensión distribuido durante el día requieren más instancias que una oleada concentrada de visitas.
* **Número de valores únicos para la dimensión**: Cada dimensión tiene un segundo umbral establecido en un valor de 2.100.000 valores únicos de forma predeterminada. Si el número de valores únicos en una dimensión supera este umbral más alto, se aplica un filtrado mucho más agresivo.

Teniendo en cuenta los factores anteriores, espere de **cientos a miles** de instancias para que un solo elemento de dimensión escape [!UICONTROL Poco tráfico] si solo se supera el primer umbral. Espere entre **miles y decenas de miles** de instancias para que un solo elemento de dimensión escape [!UICONTROL Poco tráfico] si se supera el umbral más alto. Adobe no garantiza que los elementos de dimensión escapen de forma fiable al bloque [!UICONTROL Poco tráfico]. Este concepto suele reservarse para elementos de dimensión de alto volumen inusual a finales del mes.

Cuando un elemento de dimensión escapa del bloque [!UICONTROL Poco tráfico], las instancias recopiladas antes de la afluencia de tráfico permanecen en [!UICONTROL Poco tráfico].

## Cambio de los umbrales de límite único

Los límites de umbral a veces se pueden cambiar por dimensión. Póngase en contacto con el Servicio de atención al cliente de Adobe o con su Equipo de cuenta de Adobe para solicitar este cambio. La medida en que se pueden aumentar los umbrales depende de varios factores; Adobe no garantiza que se puedan satisfacer todas las solicitudes de aumento de umbrales. Al solicitar un cambio, indique:

* El ID del grupo de informes
* La dimensión para la que desea aumentar el umbral
* El primer y el segundo umbral deseado:
   * El primer umbral (agrupamiento inicial) está establecido en **2.000.000** de forma predeterminada.
   * El segundo umbral (filtrado más agresivo) está establecido en **2,100,000** de manera predeterminada.

>[!IMPORTANT]
>
>Los cambios en los umbrales pueden afectar al rendimiento del informe. Adobe recomienda usar el buen criterio al solicitar un aumento de valores únicos para una dimensión. Aumente únicamente los límites únicos para las dimensiones que son críticas para las necesidades de creación de informes de su organización.

Los umbrales [!UICONTROL Poco tráfico] no son visibles en la interfaz de usuario de Analytics. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener más información sobre los umbrales existentes.

## Interacciones con otras capacidades

Las diferentes funcionalidades tratan los valores de [!UICONTROL Poco tráfico] de diferentes maneras.

* **Data Warehouse:** En la mayoría de los casos, no hay límite en la cantidad de valores únicos en los informes de Data Warehouse. Su arquitectura única permite generar informes de cualquier cantidad de valores únicos. Sin embargo, los valores de [!UICONTROL Poco tráfico] pueden seguir apareciendo en algunos escenarios limitados. Algunos ejemplos son variables de lista, props de lista, eVars de comercialización y dimensiones de detalle del canal de marketing.
* **Segmentación:** Si los criterios del segmento incluyen una dimensión con un número elevado de valores únicos, no se incluyen los valores capturados en [!UICONTROL Poco tráfico].
* **Clasificaciones:** los informes de clasificación también están sujetos a límites únicos. Si el elemento de dimensión principal de una clasificación se incluye en [!UICONTROL Poco tráfico], el valor no se clasifica.
   * [!UICONTROL Los valores de poco tráfico] clasificados a través del importador se pueden ver en Data Warehouse. <!-- AN-115871 -->
   * Los valores de [!UICONTROL Poco tráfico] clasificados mediante el generador de reglas *no se pueden* ver en Data Warehouse. <!-- AN-122872 -->
