---
description: Cuando un informe tiene muchos valores únicos, el Adobe utiliza el elemento de dimensión Poco tráfico para mejorar el rendimiento del informe.
title: Valor de poco tráfico en Adobe Analytics
feature: Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: ddd1473ccfe27dbcb28c0c51992628c9bf03cb5c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Valor de poco tráfico en Adobe Analytics

Cuando un informe contiene varios valores únicos, una funcionalidad incluida en Adobe permite asegurar que los valores más importantes aparezcan en el informe. Los valores de variables únicas recopilados después de aproximadamente 500 000 valores existentes se enumeran dentro de un elemento de dimensión etiquetado **[!UICONTROL Poco tráfico]**.

## Funcionamiento de [!UICONTROL Poco tráfico]

* La creación de informes no se ve afectada si la variable no alcanza los 500 000 valores únicos en un mes determinado.
* Cuando una variable alcanza los 500 000 valores únicos, los datos comienzan a agruparse en [!UICONTROL Poco tráfico]. Todos los valores que superan este umbral se rigen por la siguiente lógica:
   * Si un valor ya figura en los informes, añádalo como de costumbre.
   * Si un valor aún no aparece en los informes, inicialmente se agrupa en la variable [!UICONTROL Poco tráfico] elemento de dimensión.
   * Si un valor que está agrupado en [!UICONTROL Poco tráfico] recibe una afluencia de tráfico (normalmente instancias con dos dígitos en un solo día) y comienza a reconocerse como su propio elemento de dimensión. Las instancias recopiladas antes de alcanzar el umbral permanecen por debajo de [!UICONTROL Poco tráfico]. El umbral exacto tiene muchas dependencias, como el número de servidores que procesan datos para el grupo de informes y la cantidad de tiempo entre cada instancia de elemento de dimensión.
* Si un grupo de informes alcanza más de 1 000 000 de valores únicos, se aplica un filtrado más intenso. Los valores únicos requieren instancias con tres dígitos en un solo día antes de reconocerse como su propio elemento de dimensión.

Esta lógica permite que el Adobe optimice las funcionalidades de informes a la vez que permite a su organización informar sobre elementos de dimensión cruciales recopilados más adelante en el mes. Por ejemplo, su organización administra un sitio con millones de artículos y un nuevo artículo se hizo popular a finales de mes (después de superar ambos umbrales únicos). Aún puede analizar el rendimiento de ese artículo sin que se agrupe en [!UICONTROL Poco tráfico]. Esta lógica no pretende desagrupar todo lo que obtenga una cierta cantidad de vistas de página por día o por mes.

>[!NOTE]
>La variable [Página](../components/dimensions/page.md) la dimensión utiliza varias columnas back-end que todas cuentan para umbrales únicos, incluyendo `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`y `click_context`. Estas columnas back-end pueden causar [!UICONTROL Poco tráfico] para aplicar mucho antes de que el número de elementos de dimensión de página únicos en Workspace alcance los 500 000.

## Cambio de los umbrales de límite único

De forma predeterminada, estos umbrales son 500 000 y 1 millón de valores únicos. Estos límites se pueden cambiar según la variable. Póngase en contacto con el Servicio de atención al cliente de Adobe o con el administrador de cuentas de su organización para solicitar este cambio. Al solicitar un cambio, indique:

* El ID del grupo de informes
* La variable para la que solicita aumentar el umbral
* El primer y el segundo umbral deseado

Los cambios en los umbrales pueden afectar al rendimiento del informe. Adobe recomienda usar el buen criterio al solicitar un aumento de valores únicos en una variable. Solo aumente los límites únicos para las variables que son críticas para las necesidades de informes de su organización.

Los umbrales de poco tráfico no son visibles en la interfaz de usuario de Analytics. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener más información sobre los umbrales existentes.

## Poco tráfico con componentes y otras funciones

Las diferentes funciones tratan los valores de poco tráfico de diferentes maneras.

* **Data Warehouse:** no hay límite para la cantidad de valores únicos que pueden aparecer en los informes de Data Warehouse. Su arquitectura única permite generar informes de cualquier cantidad de valores únicos.
   * Pueden seguir apareciendo valores de poco tráfico en situaciones limitadas. Por ejemplo: las variables de lista, las props de lista, las eVars de comercialización y las dimensiones de detalle del canal de marketing.
* **Segmentación:** si los criterios del segmento contienen una variable con un número elevado de valores únicos, no se incluyen los valores capturados en tráfico bajo.
* **Clasificaciones:** los informes de clasificación también están sujetos a límites únicos. Si el valor de la variable principal de una clasificación se encuentra en poco tráfico, el valor no se clasifica.
   * Los valores de clasificación de poco tráfico obtenidos mediante el importador se pueden ver en Data Warehouse. <!-- AN-115871 -->
   * Los valores de clasificación de poco tráfico obtenidos a través del generador de reglas *no se pueden* ver en Data Warehouse. <!-- AN-122872 -->
