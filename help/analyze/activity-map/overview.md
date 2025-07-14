---
description: Clasifique la actividad de los vínculos mediante superposiciones visuales para supervisar la participación de la audiencia en las páginas web.
title: Descripción general de Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Información general de Activity Map

Activity Map es una funcionalidad de Adobe Analytics que proporciona una representación visual de la participación del usuario en páginas web y aplicaciones móviles. Permite a los especialistas en marketing y a los analistas realizar un seguimiento y analizar las interacciones del usuario, como los clics y el comportamiento de desplazamiento. Activity Map genera mapas de calor e informes de superposición que muestran los elementos más populares de una página web, lo que le ayuda a optimizar sus experiencias digitales.

Esta sección de la documentación de se centra en la superposición de Activity Map. Sin embargo, el uso de Activity Map tiene otras partes importantes:

* **Configuración del grupo de informes**: un grupo de informes debe tener Activity Map habilitado. Consulte [Informes de Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) en la configuración del grupo de informes.
* **Implementación**: La mayoría de los informes de Activity Map están disponibles de forma predeterminada. Sin embargo, algunos sitios web pueden requerir una implementación adicional para aprovechar al máximo el seguimiento de vínculos. Las siguientes variables de implementación están disponibles:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): filtrar datos de clics por nombre de vínculo.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): filtrar datos de clics por nombre de región.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): cambie el atributo que rellena la dimensión Región de Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personalice la lógica que utiliza Activity Map para rellenar la dimensión Vínculo de Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personalice la lógica que utiliza Activity Map para rellenar la dimensión Región de Activity Map.
* **Dimensiones**: Además de la extensión de superposición, Activity Map proporciona varias dimensiones que puede usar en Analysis Workspace.
   * [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md): El nombre del vínculo donde se hizo clic.
   * [Región de Activity Map](/help/components/dimensions/activity-map-region.md): El nombre de región donde se hizo clic.
   * [Página de Activity Map](/help/components/dimensions/activity-map-page.md): El nombre de la página en el momento en que se hizo clic en el vínculo.
   * [Vínculo de Activity Map por región](/help/components/dimensions/activity-map-link-by-region.md): Un valor concatenado de Vínculo de Activity Map y Región de Activity Map.

## Características y ventajas

* **Visualización de la participación del usuario**: Activity Map ofrece una representación visual dinámica del comportamiento del usuario, que le permite ver exactamente dónde hace clic. Estos datos visuales facilitan la identificación de patrones, tendencias y áreas de interés. A continuación, puede tomar decisiones informadas sobre el diseño, la ubicación del contenido y el flujo de usuarios.

* **Mapas de calor**: Activity Map genera mapas de calor que muestran las áreas de una página web en las que se hace más clic o se interactúa. Los mapas de calor utilizan códigos de color para representar el nivel de participación, lo que le permite identificar puntos clave y priorizar la atención en áreas de alto impacto. Esta información puede ser útil para optimizar botones, vínculos, formularios u otros elementos interactivos de call-to-action.

* **Informes de superposición**: Los informes de superposición de Activity Map proporcionan métricas detalladas de clics para elementos específicos de una página web. Al comprender las tasas de pulsaciones y los niveles de participación de los elementos individuales, puede ajustar sus estrategias de diseño y contenido para mejorar las experiencias de los usuarios.

* **Análisis de segmentos**: puede analizar el comportamiento del usuario en función de distintos segmentos, como fuentes de tráfico, datos demográficos o personalidades. Al segmentar los datos, puede descubrir perspectivas valiosas en grupos de usuarios específicos, lo que permite experiencias personalizadas y estrategias de marketing dirigidas.

## Aplicaciones prácticas

* **Optimización de sitios web**: Activity Map ayuda a optimizar los sitios web al identificar elementos de bajo rendimiento, mejorar la navegación y mejorar la experiencia general del usuario. Al analizar las interacciones del usuario, puede tomar decisiones basadas en datos para optimizar los flujos de usuario, simplificar los formularios o ajustar la ubicación del contenido para lograr el máximo impacto.

* **Optimización de la tasa de conversión**: al visualizar la participación del usuario y analizar las tasas de pulsaciones, Activity Map desempeña un papel crucial en los esfuerzos de CRO. Puede identificar barreras para la conversión y experimentar con diferentes variaciones de diseño para optimizar los canales de conversión, las páginas de aterrizaje y los procesos de cierre de compra.

* **Pruebas A/B**: Activity Map se puede combinar con pruebas A/B para medir el impacto de los cambios de diseño o contenido. Al comparar las métricas de participación entre diferentes versiones de una página web, puede determinar qué variaciones producen un mayor compromiso del usuario, tasas de conversión o ingresos.

