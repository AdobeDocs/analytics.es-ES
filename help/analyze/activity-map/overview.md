---
description: Clasifique la actividad de los vínculos mediante superposiciones visuales para monitorizar la participación del público en las páginas web.
title: Descripción general de Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
TQID: https://experienceleague.adobe.com/1-o8wAr6cY8jSR2facQEvh--wvXByJf6R01r4RcVEhI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 100%

---

# Información general de Activity Map

Activity Map es una funcionalidad de Adobe Analytics que proporciona una representación visual de la participación del usuario en páginas web y aplicaciones móviles. Permite a los especialistas en marketing y a los analistas hacer un seguimiento y analizar las interacciones del usuario, como los clics y el comportamiento de desplazamiento. Activity Map genera mapas de calor e informes de superposición que muestran los elementos más populares de una página web, lo que le permite optimizar sus experiencias digitales.

Activity Map como concepto consta de varios componentes importantes:

* **Configuración del grupo de informes**: un grupo de informes debe tener un Activity Map habilitado para que pueda empezar a utilizarlo. Consulte [Creación de informes de Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) en la configuración del grupo de informes.
* **Implementación**: La mayoría de la creación de informes de Activity Map está disponible de forma predeterminada. Sin embargo, algunos sitios web pueden requerir una implementación adicional para aprovechar al máximo el seguimiento de vínculos. Las variables de implementación siguientes están disponibles:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtre datos de clics por nombre de vínculo.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtre datos de clics por nombre de región.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): Cambie el atributo que rellena la dimensión Región de Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): Personalice la lógica que utiliza Activity Map para rellenar la dimensión Vínculo de Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): Personalice la lógica que utiliza Activity Map para rellenar la dimensión Región de Activity Map.
* **Superposición**: Una extensión del explorador que le permite ver datos de clics superpuestos en el sitio web. Consulte [Interfaz de extensión de Activity Map](overlay/overview.md) para obtener más información. Esta función no está disponible para implementaciones de SDK web.
* **Dimensiones**: Además de la extensión de superposición, Activity Map proporciona varias dimensiones que puede usar en Analysis Workspace.
   * [Vínculo de Activity Map](/help/components/dimensions/activity-map-link.md): El nombre del vínculo donde se hizo clic.
   * [Región de Activity Map](/help/components/dimensions/activity-map-region.md): El nombre de la región donde se hizo clic.
   * [Página de Activity Map](/help/components/dimensions/activity-map-page.md): El nombre de la página en el momento en que se hizo clic en el vínculo.
   * [Vínculo de Activity Map por región](/help/components/dimensions/activity-map-link-by-region.md): Un valor concatenado de vínculo de Activity Map y la región de Activity Map.

## Funciones y ventajas

* **Visualización de la participación del usuario**: Activity Map ofrece una representación visual dinámica del comportamiento del usuario que le permite ver exactamente dónde hace clic. Estos datos visuales facilitan la identificación de patrones, tendencias y áreas de interés. A continuación, puede tomar decisiones fundadas sobre el diseño, la ubicación del contenido y el flujo de usuarios.

* **Mapas de calor**: Activity Map genera mapas de calor que muestran las áreas de una página web en las que se hace más clic o se interactúa. Los mapas de calor utilizan códigos de color para representar el nivel de participación, lo que permite a las empresas identificar puntos clave y priorizar la atención en áreas de gran impacto. Esta información puede ser muy valiosa para optimizar los botones de llamada a la acción, vínculos, formularios o cualquier otro elemento interactivo.

* **Informes de superposición**: Los informes de superposición de Activity Map proporcionan métricas de clic detalladas para elementos específicos de una página web. Al comprender las tasas de clics y los niveles de participación de los elementos individuales, puede ajustar su diseño y sus estrategias de contenido para mejorar las experiencias de los usuarios. Esta función no está disponible para implementaciones de SDK web.

* **Análisis de segmentos**: Puede analizar el comportamiento del usuario en función de distintos segmentos, como fuentes de tráfico, datos demográficos o perfiles. Al segmentar los datos, puede descubrir información útil sobre grupos de usuarios específicos, lo que permite experiencias personalizadas y estrategias de marketing segmentadas.

## Aplicaciones prácticas

* **Optimización del sitio web**: Activity Map le ayuda a optimizar sus sitios web mediante la identificación de elementos de bajo rendimiento, la mejora de la navegación y la mejora de la experiencia general del usuario. Al analizar las interacciones de los usuarios, puede tomar decisiones basadas en datos para optimizar los flujos de usuarios, simplificar los formularios o ajustar la ubicación del contenido para lograr el máximo impacto.

* **Optimización de la tasa de conversión (CRO)**: Al visualizar la participación del usuario y analizar las tasas de clics, Activity Map desempeña un papel crucial en los esfuerzos de CRO. Puede identificar barreras para la conversión y experimentar con diferentes variaciones de diseño para optimizar los embudos de conversión, las páginas de destino y los procesos de cierre de compra.

* **Prueba A/B**: Se puede combinar Activity Map con pruebas A/B para medir el impacto de los cambios de diseño o contenido. Al comparar las métricas de participación entre las distintas versiones de una página web, puede determinar qué variaciones producen un aumento en la participación del usuario, las tasas de conversión o los ingresos.

