---
description: Cuando un informe tiene muchos valores únicos, Adobe utiliza el elemento de dimensión Poco tráfico para mejorar el rendimiento del informe.
title: Valor de poco tráfico en Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: fe6b1a2d503bbc423d3ebcacad2ce3c29e1ebbed
workflow-type: ht
source-wordcount: '864'
ht-degree: 100%

---

# Valor de poco tráfico en Adobe Analytics

Cuando un informe contiene varios valores únicos, una funcionalidad incluida en Adobe permite asegurar que los valores más importantes aparezcan en el informe. Los valores de variables únicas recopilados más allá de un determinado umbral (consulte a continuación) se muestran con un elemento de dimensión etiquetado como **[!UICONTROL Poco tráfico]**.

## Funcionamiento de [!UICONTROL Poco tráfico]

* Adobe Analytics utiliza dos umbrales para determinar qué valores únicos se muestran en los informes cada mes: un **[!UICONTROL umbral bajo]** y un **[!UICONTROL umbral alto]**. Adobe puede ajustar estos umbrales periódicamente. Los límites de umbral actuales son:
   * **[!UICONTROL Umbral bajo]**: >500 000 valores únicos durante el mes.
   * **[!UICONTROL Umbral alto]**: >1 000 000 de valores únicos durante el mes.
* A **mediados de abril de 2024**, Adobe empezará a aumentar los umbrales de bajo tráfico predeterminados del grupo de informes de la siguiente manera: ![umbrales de bajo tráfico](assets/thresholds.png) 
Esto afectará únicamente a las variables que actualmente están configuradas por debajo de los nuevos umbrales. Estos cambios se introducirán gradualmente y esperamos que el trabajo esté terminado a **finales de mayo**. A medida que se vayan aplicando estos incrementos, es posible que note cambios en las variables de alta cardinalidad:<ul><li>Puede haber más valores de dimensión disponibles para la creación de informes.</li><li>Los segmentos y las métricas calculadas pueden incluir más datos.</li><li>Los conjuntos de informes virtuales basados en segmentos pueden incluir más datos.</li><li>Las exportaciones de clasificación pueden incluir más datos.</li></ul>
* La creación de informes no se ve afectada si la variable no alcanza el umbral bajo en un mes determinado.
* Cuando una variable alcanza el umbral bajo, los datos comienzan a agruparse en bloques de [!UICONTROL poco tráfico]. Todos los valores que superan este umbral se rigen por la siguiente lógica:
   * Si un valor ya figura en los informes, añádalo como de costumbre.
   * Si un valor aún no aparece en los informes, inicialmente se agrupará en el elemento de dimensión [!UICONTROL Poco tráfico]. 
   * Si un valor que está agrupado en [!UICONTROL Poco tráfico] recibe una afluencia de tráfico (normalmente instancias de dos dígitos en un solo día), comienza a reconocerse como su propio elemento de dimensión. Las instancias recopiladas antes de alcanzar el umbral permanecen como [!UICONTROL Poco tráfico]. El punto exacto en el que el elemento de dimensión empieza a mostrarse en los informes tiene muchas dependencias, como el número de servidores que procesan datos para el grupo de informes y la cantidad de tiempo entre cada instancia de elemento de dimensión.
* Si una variable alcanza el umbral alto, se aplica un filtrado más agresivo. Los valores únicos requieren instancias de tres dígitos en un solo día antes de reconocerse como su propio elemento de dimensión.

Esta lógica permite a Adobe optimizar las capacidades de creación de informes al tiempo que permite a la organización crear informes sobre los elementos de dimensión cruciales recopilados más adelante en el mes. Por ejemplo, si su organización ejecuta un sitio con millones de artículos y un nuevo artículo se vuelve popular hacia el final del mes (después de superar ambos umbrales únicos), aún puede analizar el rendimiento de ese artículo sin que se agrupe bajo [!UICONTROL Poco tráfico]. La lógica no pretende desagrupar todo lo que recibe un determinado número de visitas de página al día o al mes.

>[!NOTE]
>La dimensión [Página](../components/dimensions/page.md) utiliza varias columnas de back-end, y todas cuentan hacia umbrales únicos, como `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, y `click_context`. Estas columnas back-end pueden causar que la lógica [!UICONTROL Poco tráfico] se aplique mucho antes de que el número de elementos de dimensión de página únicos en Workspace alcance el umbral bajo.

Tenga en cuenta que la lógica de poco tráfico descrita anteriormente funciona mejor con variables que tienen elementos de dimensión que se repiten muchas veces durante el mes. Si los elementos de dimensión de una variable son casi o totalmente únicos en cada visita, la variable alcanzará el umbral bajo rápidamente y todos los nuevos elementos de dimensión del mes terminarán en el bloque de poco tráfico.

## Cambio de los umbrales de límite único

Estos límites de umbral a veces se pueden cambiar según la variable. Póngase en contacto con el Servicio de atención al cliente de Adobe o con su Equipo de cuenta de Adobe para solicitar este cambio. La medida en que pueden aumentarse los umbrales depende de varios factores y es posible que Adobe no pueda adaptarse a los aumentos de los umbrales en todos los casos. Al solicitar un cambio, indique:

* El ID del grupo de informes
* La variable para la que solicita aumentar el umbral
* El primer y el segundo umbral deseado

Los cambios en los umbrales pueden afectar al rendimiento del informe. Adobe recomienda usar el buen criterio al solicitar un aumento de valores únicos en una variable. Aumente únicamente los límites únicos de las variables que son esenciales para las necesidades de creación de informes de su organización.

Los umbrales de poco tráfico no son visibles en la interfaz de usuario de Analytics. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener más información sobre los umbrales existentes.

## Poco tráfico con componentes y otras funciones

Las diferentes funciones tratan los valores de poco tráfico de diferentes maneras.

* **Data Warehouse:** no hay límite para la cantidad de valores únicos que pueden aparecer en los informes de Data Warehouse. Su arquitectura única permite generar informes de cualquier cantidad de valores únicos.
   * Pueden seguir apareciendo valores de poco tráfico en situaciones limitadas. Por ejemplo: las variables de lista, las props de lista, las eVars de comercialización y las dimensiones de detalle del canal de marketing.
* **Segmentación:** si los criterios del segmento contienen una variable con un número elevado de valores únicos, no se incluyen los valores capturados en tráfico bajo.
* **Clasificaciones:** los informes de clasificación también están sujetos a límites únicos. Si el valor de la variable principal de una clasificación se encuentra en poco tráfico, el valor no se clasifica.
   * Los valores de clasificación de poco tráfico obtenidos mediante el importador se pueden ver en Data Warehouse. <!-- AN-115871 -->
   * Los valores de clasificación de poco tráfico obtenidos a través del generador de reglas *no se pueden* ver en Data Warehouse. <!-- AN-122872 -->
