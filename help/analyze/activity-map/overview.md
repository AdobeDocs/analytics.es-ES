---
description: Clasifique la actividad de los vínculos mediante superposiciones visuales para supervisar la participación de la audiencia en las páginas web.
title: Descripción general de Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 4%

---

# Información general de Activity Map

Activity Map es una funcionalidad de Adobe Analytics que proporciona una representación visual de la participación del usuario en páginas web y aplicaciones móviles. Permite a los especialistas en marketing y a los analistas realizar un seguimiento y analizar las interacciones del usuario, como los clics y el comportamiento de desplazamiento. Activity Map genera mapas de calor e informes de superposición que muestran los elementos más populares de una página web, lo que le ayuda a optimizar sus experiencias digitales.

Esta sección de la documentación de se centra en la superposición de Activity Map. Sin embargo, hay otras partes importantes en el uso de Activity Map:

* **Configuración del grupo de informes**: un grupo de informes debe tener habilitado el Activity Map. Consulte [Informes de Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) en la configuración del grupo de informes.
* **Implementación**: La mayoría de los informes de Activity Map están disponibles de forma predeterminada. Sin embargo, algunos sitios web pueden requerir una implementación adicional para aprovechar al máximo el seguimiento de vínculos. Las siguientes variables de implementación están disponibles:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): filtrar datos de clics por nombre de vínculo.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): filtrar datos de clics por nombre de región.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): cambie el atributo que rellena la dimensión Región del Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personalice la lógica que utiliza el Activity Map para rellenar la dimensión Vínculo de Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personalice la lógica que utiliza el Activity Map para rellenar la dimensión Región del Activity Map.
* **Dimension**: además de la extensión de superposición, Activity Map proporciona varias dimensiones que puede usar en Analysis Workspace.
   * [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md): Nombre del vínculo en el que se hizo clic.
   * [Región Activity Map](/help/components/dimensions/activity-map-region.md): El nombre de región donde se hizo clic.
   * [Página de Activity Map](/help/components/dimensions/activity-map-page.md): El nombre de la página en el momento en que se hizo clic en el vínculo.
   * [Vínculo de Activity Map por región](/help/components/dimensions/activity-map-link-by-region.md): Valor concatenado de Vínculo de Activity Map y Región de Activity Map.

## Características y ventajas

* **Visualización de la participación del usuario**: Activity Map ofrece una representación visual dinámica de la conducta del usuario, lo que le permite ver exactamente dónde hacen clic los usuarios. Estos datos visuales facilitan la identificación de patrones, tendencias y áreas de interés. A continuación, puede tomar decisiones informadas sobre el diseño, la ubicación del contenido y el flujo de usuarios.

* **Mapas de calor**: el Activity Map genera mapas de calor que muestran las áreas de una página web en las que se hace más clic o se interactúa. Los mapas de calor utilizan códigos de color para representar el nivel de participación, lo que le permite identificar puntos clave y priorizar la atención en áreas de alto impacto. Esta información puede ser útil para optimizar botones de llamada a la acción, vínculos, formularios u otros elementos interactivos.

* **Informes de superposición**: Los informes de superposición del Activity Map proporcionan métricas detalladas de clics para elementos específicos de una página web. Al comprender las tasas de pulsaciones y los niveles de participación de los elementos individuales, puede ajustar sus estrategias de diseño y contenido para mejorar las experiencias de los usuarios.

* **Análisis de segmentos**: puede analizar el comportamiento del usuario en función de distintos segmentos, como fuentes de tráfico, datos demográficos o personalidades. Al segmentar los datos, puede descubrir perspectivas valiosas en grupos de usuarios específicos, lo que permite experiencias personalizadas y estrategias de marketing dirigidas.

## Aplicaciones prácticas

* **Optimización de sitios web**: el Activity Map le ayuda a optimizar sus sitios web al identificar elementos de bajo rendimiento, mejorar la navegación y mejorar la experiencia general del usuario. Al analizar las interacciones del usuario, puede tomar decisiones basadas en datos para optimizar los flujos de usuario, simplificar los formularios o ajustar la ubicación del contenido para lograr el máximo impacto.

* **Optimización de la tasa de conversión**: al visualizar la participación del usuario y analizar las tasas de pulsaciones, el Activity Map desempeña un papel crucial en los esfuerzos de CRO. Puede identificar barreras para la conversión y experimentar con diferentes variaciones de diseño para optimizar los canales de conversión, las páginas de aterrizaje y los procesos de cierre de compra.

* **Pruebas A/B**: el Activity Map se puede combinar con pruebas A/B para medir el impacto de los cambios de diseño o contenido. Al comparar las métricas de participación entre diferentes versiones de una página web, puede determinar qué variaciones producen un mayor compromiso del usuario, tasas de conversión o ingresos.

* **Optimización de aplicaciones móviles**: Activity Map no se limita a los sitios web, sino que también extiende su funcionalidad a las aplicaciones móviles. Puede obtener información sobre las interacciones de los usuarios dentro de las aplicaciones, lo que les permite mejorar la facilidad de uso, la navegación y las funciones para disfrutar de una experiencia móvil perfecta.
