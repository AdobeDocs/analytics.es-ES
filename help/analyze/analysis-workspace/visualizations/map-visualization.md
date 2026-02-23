---
description: Utilice la visualización de mapas para trazar datos en una visualización de mapa geográfico.
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 62%

---

# Mapa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mapa"
>abstract="Esta visualización representa las métricas superponiéndolas en un mapa. Esta visualización resulta útil para identificar datos en diferentes regiones geográficas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Burbujas"
>abstract="Trace eventos con burbujas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Mapa térmico"
>abstract="Trace eventos con un mapa térmico."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización de mapas en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Mapa](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/map) para la_ versión de ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** de este artículo._

>[!ENDSHADEBOX]



La visualización ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL Mapa]** en Analysis Workspace

* permite crear un mapa visual de cualquier métrica (incluidas las métricas calculadas),
* resulta útil para identificar y comparar datos de métricas entre distintas regiones geográficas,
* admite dos fuentes de datos: latitud/longitud para el uso desde dispositivos móviles o dimensión geográfica para el uso en web,
* admite exportación de PDF, y
* aprovecha WebGL para la visualización de gráficos. Si sus controladores gráficos no admiten la representación WebGL, es posible que deba actualizarlos.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualización de mapa en Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/map-visualization){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Usar

1. Añada una visualización ![Mapa](/help/assets/icons/Globe.svg) [!UICONTROL Mapa]. Consulte [Añadir una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Solo puede arrastrar una visualización de mapa sobre una tabla de forma libre.

   ![Configuración de mapa](assets/map-configuration.png){width="50%"}

1. En las listas desplegables, seleccione una métrica. Arrastre una métrica desde la lista de métricas (incluidas métricas calculadas).
1. Especifique la fuente de datos que desea utilizar. Este cuadro de diálogo aparece únicamente si tiene habilitado el seguimiento de la ubicación para datos de aplicaciones móviles.

   | Fuente | Descripción |
   | --- | --- |
   | **[!UICONTROL Latitud/Longitud móvil]** | Esta opción representa los datos de las aplicaciones móviles. Solo verá esta opción si la ha habilitado para su conjunto de informes en [!UICONTROL Analytics] > [!UICONTROL Administración] > [!UICONTROL Grupos de informes] > (seleccione el grupo de informes)> [!UICONTROL Editar configuración] >  [!UICONTROL Administración móvil] > [!UICONTROL Activar el seguimiento de ubicación]. Esta configuración es la predeterminada (si el seguimiento de la ubicación está habilitado). |
   | **[!UICONTROL Dimensión geográfica]** | Esta opción representa los datos de segmentación geográfica según la ubicación de los visitantes, en función de su dirección IP. Estos datos se transforman en [!UICONTROL País], [!UICONTROL Región] y [!UICONTROL Ciudad]. Tenga en cuenta que no se desciende al nivel del código postal ni DMA. Casi todos los grupos de informes tienen habilitada esta dimensión. Si no es así, póngase en contacto con el Servicio de atención al cliente de Adobe para activar los informes geográficos. |

1. Seleccione **[!UICONTROL Generar]**.

   Se genera una visualización de mapa del mundo con burbujas.

   ![](assets/bubble-world-view.png)

1. Ahora puede hacer lo siguiente:

   * **Haz zoom** en este mapa para ampliar ciertas áreas al hacer doble clic en el mapa o al usar la rueda de desplazamiento. El mapa se amplía según la posición del cursor. Mediante la interacción de zoom, la dimensión requerida (país > estado > ciudad) se actualiza automáticamente en función del nivel de zoom.
   * **Compare** dos o más visualizaciones de mapas en el mismo proyecto colocándolas una al lado de la otra.
   * **Mostrar comparaciones período tras período (por ejemplo, año tras año)**:

      * Mostrar números negativos: por ejemplo, si planea crear una métrica año tras año, el mapa puede mostrar -33 % en Nueva York.
      * En cuanto a las métricas que son de tipo *por ciento*, el clústering calcula la media total de los porcentajes.
      * Un esquema de colores verde/rojo: positivo/negativo

   * **Gira** el mapa en 2D o 3D manteniendo presionada la tecla [!UICONTROL Ctrl] y moviendo el mapa.

   * **Cambiar** a una vista diferente, como el mapa de calor, usando la [configuración](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) que se describe a continuación. Tenga en cuenta que la vista de burbujas es la configuración predeterminada.

1. **Guarde** el proyecto para guardar toda la configuración del mapa (coordenadas, zoom, rotación).
1. La tabla de forma libre, bajo la visualización, puede rellenarse arrastrando a ella dimensiones de localización y métricas desde el carril izquierdo:



## Configuración

Para reconfigurar la visualización del mapa, seleccione ![Editar](/help/assets/icons/Edit.svg).


## Configuración

Para definir la configuración de la visualización, seleccione ![Configuración](/help/assets/icons/Setting.svg).

| Configuración | Descripción |
|--- |--- |
| **[!UICONTROL Tipo de mapa]** | |
| **[!UICONTROL Burbujas] | Traza eventos con burbujas. Un gráfico de burbujas es un gráfico de varias variables que es una cruz entre un diagrama de dispersión y un gráfico de área proporcional. Esta es la vista predeterminada. |
| [!UICONTROL Mapa de calor] | Traza eventos mediante un mapa de calor. Un mapa de calor es una representación gráfica de datos en la que los valores individuales contenidos en una matriz se representan como colores. |
| **[!UICONTROL Estilos]** | |
| [!UICONTROL Tema de color] | Muestra el esquema de colores para el mapa de calor y las burbujas. Puedes elegir entre Coral, Rojos, Verdes o Azules. El color predeterminado es Coral. |
| [!UICONTROL Estilo de mapa] | Puede elegir entre Básico, Calles, Brillante, Claro, Oscuro y Satélite. |
| **[!UICONTROL Radio de clúster]** | Agrupar los puntos de datos que se hallan dentro de un radio de píxeles definido. El valor predeterminado es 50. |
| **[!UICONTROL Valor máx. personalizado]** | Le permite alterar el umbral para el valor máximo del mapa. Al ajustar este valor, se ajusta la escala de los valores (color y tamaño) de las burbujas/mapa de calor en relación con el valor máximo personalizado establecido. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/build-a-time-parting-heatmap)

-->

