---
description: Utilice la visualización de mapas en un proyecto de Workspace.
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: e0d14f6dd7be438f3dad979abcfc279e710873e7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 62%

---

# Mapa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mapa"
>abstract="Esta visualización representa las métricas superponiéndolas en un mapa. Resulta útil para identificar datos en diferentes regiones geográficas."

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

_Este artículo documenta la visualización de mapas en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Actualmente no hay ninguna visualización de mapas disponible en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]



La visualización ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** en Analysis Workspace

* le permite crear un mapa visual de cualquier métrica (incluidas las métricas calculadas),
* es útil para identificar y comparar datos de métricas en diferentes regiones geográficas,
* puede admitir 2 fuentes de datos: latitud/longitud desde uso móvil o dimensión geográfica para uso web,
* admite la exportación de PDF, y
* aprovecha WebGL para la visualización de gráficos. Si sus controladores gráficos no admiten la representación WebGL, es posible que deba actualizarlos.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualización de mapas en Analysis Workspace](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Utiliza

1. Agregue una visualización ![Map](/help/assets/icons/Globe.svg) [!UICONTROL Map]. Consulte [Agregar una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Solo puede arrastrar una visualización de mapa sobre una tabla de forma libre.

   ![Configuración de mapa](assets/map-configuration.png){width="50%"}

1. En las listas desplegables, seleccione una métrica. O bien, arrastre una métrica desde la lista de métricas (incluidas las métricas calculadas).
1. Especifique el origen de datos desde el que desea dibujar. Este cuadro de diálogo solo aparece si tiene habilitado el seguimiento de ubicación para los datos de aplicaciones móviles.

   | Fuente | Descripción |
   | --- | --- |
   | **[!UICONTROL Latitud/Longitud móvil]** | Esta opción representa los datos de las aplicaciones móviles. Solo verá esta opción si la ha habilitado para su conjunto de informes en [!UICONTROL Analytics] > [!UICONTROL Administración] > [!UICONTROL Grupos de informes] > (seleccione el grupo de informes)> [!UICONTROL Editar configuración] >  [!UICONTROL Administración móvil] > [!UICONTROL Activar el seguimiento de ubicación]. Esta configuración es la predeterminada (si el seguimiento de la ubicación está habilitado). |
   | **[!UICONTROL Dimensión geográfica]** | Esta opción representa los datos de segmentación geográfica según la ubicación de los visitantes, en función de su dirección IP. Estos datos se transforman en [!UICONTROL País], [!UICONTROL Región] y [!UICONTROL Ciudad]. Tenga en cuenta que no se desciende al nivel del código postal ni DMA. Casi todos los grupos de informes tienen habilitada esta dimensión. Si no es así en su caso, póngase en contacto con el Servicio de atención al cliente de Adobe para habilitar los informes geográficos. |

1. Seleccione **[!UICONTROL Generar]**.

   Se genera una visualización de mapa del mundo con burbujas.

   ![](assets/bubble-world-view.png)

1. Ahora puede:

   * **Hacer zoom** en este mapa para ampliar determinadas áreas haciendo doble clic en el mapa o utilizando la rueda de desplazamiento. El mapa se amplía o se reduce según dónde haya colocado el cursor. La dimensión requerida (país > estado > ciudad) se actualiza automáticamente según la interacción con el nivel de zoom.
   * **Comparar** dos o más visualizaciones de mapas en el mismo proyecto colocándolas una al lado de la otra.
   * **Mostrar comparaciones entre períodos (por ejemplo, año tras año)**:

      * Mostrar números negativos: por ejemplo, si planea crear una métrica año tras año, el mapa puede mostrar -33 % en Nueva York.
      * Con métricas del tipo *percent*, la agrupación reúne los porcentajes según la media.
      * Esquema de colores verde/rojo: positivo/negativo

   * **Girar** el mapa en 2D o 3D manteniendo presionada la tecla [!UICONTROL Ctrl] y desplazando el mapa.

   * **Alternar** entre las distintas vistas, como el mapa de calor, empleando las [configuraciones](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas más adelante. La visualización de burbujas es la configuración predeterminada.

1. **Guardar** el proyecto para guardar la configuración completa del mapa (coordenadas, zoom, rotación).
1. La tabla de forma libre, debajo de la visualización, se puede rellenar arrastrando dimensiones de ubicación y métricas desde el carril izquierdo.



## Configuración

Para reconfigurar la visualización Mapa, seleccione ![Editar](/help/assets/icons/Edit.svg).


## Configuración

Para definir la configuración de la visualización, seleccione ![Configuración](/help/assets/icons/Setting.svg).

| Configuración | Descripción |
|--- |--- |
| **[!UICONTROL Tipo de mapa]** | |
| [!UICONTROL Burbujas] | Representa los eventos mediante burbujas. Un gráfico de burbujas es un gráfico multivariable a medio camino entre un diagrama de dispersión y un gráfico de superficie proporcional. Esta vista es la predeterminada. |
| Mapa térmico | Representa los eventos mediante un mapa de calor. Se trata de una representación gráfica de datos que muestra como colores los valores individuales contenidos en una matriz. |
| **[!UICONTROL Estilos]** | |
| [!UICONTROL Tema de color] | Muestra el esquema de colores para el mapa de calor y las burbujas. Puede elegir entre Coral, Rojos, Verdes o Azules. El valor predeterminado es Coral. |
| [!UICONTROL Estilo de mapa] | Puede elegir entre Básico, Calles, Brillante, Claro, Oscuro y Satélite. |
| **[!UICONTROL Radio de clúster]** | Agrupa los puntos de datos que se hallan dentro de un radio de píxeles definido. El valor predeterminado es 50. |
| **[!UICONTROL Valor máximo personalizado]** | Le permite alterar el umbral para el valor máximo del mapa. Al ajustar este valor, se ajusta la escala de los valores (color y tamaño) de las burbujas/mapa de calor en relación con el valor máximo personalizado establecido. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

