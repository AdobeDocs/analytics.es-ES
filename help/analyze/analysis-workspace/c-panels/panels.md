---
description: Un panel es una colección de tablas y visualizaciones
title: Resumen de paneles
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 68%

---

# Resumen de paneles

Un [!UICONTROL panel] es una colección de tablas y visualizaciones. Puede acceder a los paneles desde el icono superior izquierdo de Workspace o desde una [panel en blanco](blank-panel.md). Los paneles son útiles cuando desea organizar sus proyectos según períodos de tiempo, grupos de informes o casos de uso de análisis.

## Tipos de panel

A continuación, se describen los tipos de paneles que están disponibles en Analysis Workspace:

| Nombre del panel | Descripción |
| --- | --- |
| [Panel en blanco](blank-panel.md) | Elija entre los paneles y las visualizaciones disponibles para iniciar el análisis. |
| [Panel de información rápida](quickinsight.md) | Cree rápidamente una tabla de forma libre y una visualización complementaria para analizar y descubrir información de manera más rápida. |
| [Panel de Analytics for Target](a4t-panel.md) | Analizar actividades y experiencias de Target en Analysis Workspace. |
| [Panel de Attribution](attribution.md) | Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión. |
| [Panel de forma libre](freeform-panel.md) | Realice comparaciones y desgloses ilimitados y, a continuación, añada visualizaciones para contar una historia de datos enriquecida. |
| [Panel de Audiencia promedio por minuto de medios](average-minute-audience-panel.md) | Analice la audiencia promedio por minuto a lo largo del tiempo, con detalles sobre los picos de visualizaciones y la capacidad de desglosar datos y compararlos. |
| [Panel de visualizadores simultáneos de medios](media-concurrent-viewers.md) | Analice los visualizadores simultáneos a lo largo del tiempo, con detalles sobre la frecuencia máxima de acceso y la capacidad de desglosar datos y compararlos. |
| [Panel Tiempo invertido en la reproducción de medios](media-playback-timespent/media-playback-time-spent.md) | Analice los visualizadores simultáneos a lo largo del tiempo, con detalles sobre la frecuencia máxima de acceso y la capacidad de desglosar datos y compararlos. |
| [panel de comparación de segmentos](c-segment-comparison/segment-comparison.md) | Compare rápidamente dos segmentos en todos los puntos de datos para encontrar automáticamente diferencias relevantes. |

![](assets/panel-overview.png)

Los paneles [!UICONTROL Información rápida], [!UICONTROL En blanco] y [!UICONTROL Forma libre] son excelentes puntos de partida para sus análisis, mientras que los paneles [!UICONTROL Analytics for Target], [!UICONTROL Attribution IQ], [!UICONTROL Visualizadores simultáneos de medios] y [!UICONTROL Comparación de segmentos] están pensados para análisis más avanzados. Hay un botón `"+"` disponible en los proyectos para que pueda agregar paneles en blanco en cualquier momento.

El panel inicial predeterminado es [!UICONTROL Forma libre], pero también puede convertir el [Panel en blanco](/help/analyze/analysis-workspace/c-panels/blank-panel.md) en el panel predeterminado.

## Grupo de informes {#report-suite}

Las tablas y visualizaciones de un panel derivan datos del [!UICONTROL grupo de informes] seleccionado en la parte superior derecha del panel. El grupo de informes también determina qué componentes están disponibles en el carril izquierdo. Dentro de un proyecto, puede utilizar uno o [varios grupos de informes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=es) en función de los casos de uso del análisis. Para aplicar un solo grupo de informes a todos los paneles de un proyecto, **haga clic con el botón derecho en el encabezado del panel > Aplicar grupo de informes a todos los paneles**.

La lista de los grupos de informes se ordena según la relevancia que Adobe define en función de la frecuencia y la antigüedad de utilización del grupo por parte del usuario, así como de la frecuencia con que se usa en la organización.

![](assets/panel-report-suite.png)

## Calendario {#calendar}

El calendario del panel controla el intervalo de la creación de informes de las tablas y visualizaciones de un panel.

>[!NOTE]
>Si se utiliza un componente de intervalo de fecha (púrpura) en una tabla, una visualización o en la zona de colocación del panel, se anula el calendario del panel.

![](assets/panel-calendar.png)

Puede aplicar un intervalo de fechas de nivel de minuto bajo la configuración avanzada del calendario del panel. Si realiza informes en un intervalo de fechas que abarca muchos días, la hora de inicio se aplica al primer día y la hora de finalización se aplica al último día del intervalo.

## Zona de colocación {#dropzone}

La zona de colocación del panel permite aplicar filtros de segmentos y desplegables a todas las tablas y visualizaciones dentro de un panel. Puede aplicar uno o varios filtros a un panel. El título sobre cada filtro se puede modificar haciendo clic en el lápiz de edición, o bien puede hacer clic con el botón derecho para eliminarlo por completo.

### Filtros de segmentos

Arrastre y suelte cualquier segmento del carril izquierdo en la zona desplegable del panel para empezar a filtrar el panel.

![Filtro](/help/admin/admin/assets/filter.png)

### Filtros de segmento ad hoc

Los componentes que no son de segmento también se pueden arrastrar directamente a la zona de colocación para crear segmentos ad hoc, lo que le ahorra tiempo y esfuerzo al ir al Generador de segmentos. Los segmentos creados de esta manera se definen automáticamente como segmentos de nivel de visita individual. Puede modificar esta definición haciendo clic en el icono de información (i) junto al segmento, seleccionando el icono de edición con forma de lápiz y editándola en el Generador de segmentos.

Los segmentos ad hoc son un tipo de segmento rápido y son locales para el proyecto. No aparecen en el carril izquierdo a menos que los haga públicos.

Para obtener más información, consulte [Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Filtros desplegables estáticos

Los filtros desplegables permiten interactuar con los datos de forma controlada. Por ejemplo, puede añadir un filtro desplegable para tipos de dispositivos móviles para poder segmentar el panel por dispositivos de tableta, teléfonos móviles o equipos de escritorio.

Los filtros desplegables también se pueden utilizar para consolidar muchos proyectos en uno. Por ejemplo, si tiene muchas versiones del mismo proyecto con diferentes segmentos de país aplicados, puede consolidar todas las versiones en un único proyecto y añadir un filtro desplegable de país.

![](assets/dropdown-filter-intro.png)

Para crear un filtro desplegable estático:

* Para los filtros desplegables que utilizan elementos de dimensión, haga clic en el icono de flecha derecha situado junto a la dimensión deseada en el carril izquierdo. Esta acción expone todos los elementos de dimensión disponibles. Seleccionar varios elementos de dimensión de esta lista mediante `[Shift + Click]` o `[Ctrl + Click]`y, a continuación, suéltelos en la zona desplegable del panel **mientras mantenga`[Shift]`**.
* Para los filtros desplegables que utilizan otros componentes, como métricas, segmentos o intervalos de fechas, seleccione varios componentes mediante `[Shift + Click]` o `[Ctrl + Click]`. Coloque la selección en la zona desplegable del panel **mientras mantenga`[Shift]`**. Todos los tipos de componentes se tratan como segmentos en este contexto.
* Un filtro desplegable único solo puede contener un tipo de componente único. Si incluye varios tipos de componentes en la selección, se crea un filtro desplegable independiente por tipo de componente. Por ejemplo, si incluye métricas y elementos de dimensión en la selección, se crean dos filtros desplegables independientes. Un filtro desplegable incluye elementos de dimensión y el otro incluye métricas.

Seleccione una de las opciones de la lista desplegable para cambiar los datos del panel. También puede optar por no filtrar ninguno en los datos del panel seleccionando **[!UICONTROL Sin filtro]**.

![](assets/create-dropdown.png)

Al hacer clic con el botón derecho en un filtro desplegable se proporcionan las siguientes opciones:

* **[!UICONTROL Agregar etiqueta]**: Al agregar un filtro desplegable a un proyecto, se establece automáticamente una etiqueta en el nombre del componente. Si elimina la etiqueta, puede agregarla de nuevo con esta opción.
* **[!UICONTROL Eliminar etiqueta]**: Elimine el texto encima de un filtro desplegable.
* **[!UICONTROL Eliminar filtro desplegable]**: Quita el filtro desplegable del panel.

[Vea el vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=es) para obtener más información sobre cómo añadir filtros desplegables al proyecto.

<!--### Dynamic drop-down filters

Dynamic drop-down filters allow you to determine available values based on data within the panel's reporting range and values in other drop-down filters. For example, you can create two dynamic drop-downs using the [Countries](/help/components/dimensions/countries.md) dimension and [Cities](/help/components/dimensions/cities.md) dimension. When you select a country from the [!UICONTROL Countries] drop-down list, the [!UICONTROL Cities] drop-down list dynamically adjusts to only show cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected filters are visible. Dimension items selected in static drop-down filters affect available values in dynamic drop-down filters. However, the inverse is not true; Dimension items selected in dynamic drop-down filters do not affect available values in static drop-down filters.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down filter so that it does not contain a value, allowing other dynamic drop-down filters to contain more values. Select **[!UICONTROL Clear All]** to clear the selection from all drop-down filters for that panel.

To create a dynamic drop-down filter:

* Drag and drop a single dimension into the panel dropzone **while holding `[Shift]`**.
* Dynamic drop-down filters are not available for metrics, segments, or date ranges.
* Right-click a drop-down filter and select **[!UICONTROL Delete filter]** to delete it.

Right-clicking a dynamic drop-down filter provides the same options as static drop-down filters.-->

## Menú contextual {#right-click}

Para obtener más funcionalidades, haga clic con el botón derecho en el encabezado del panel.

![Menú contextual](assets/right-click-menu.png)

Las configuraciones disponibles son las siguientes:

| Configuración | Descripción |
| --- | --- |
| Insertar panel copiado/visualización | Le permite pegar (&quot;insertar&quot;) un panel copiado o una visualización en otro lugar dentro del proyecto o en otro proyecto. |
| Copiar panel | Le permite hacer clic con el botón derecho y copiar un panel, de modo que pueda insertarlo en otro lugar dentro del proyecto o en otro proyecto. |
| Aplicar grupo de informes a todos los paneles | Permite aplicar el grupo de informes del panel activo a todos los paneles del proyecto. |
| Duplicar panel | Crea un duplicado exacto del panel actual que podrá modificar a continuación. |
| Contraer/expandir todos los paneles | Contrae y expande todos los paneles del proyecto. |
| Contraer/expandir todas las visualizaciones del panel | Contrae y expande todas las visualizaciones del panel actual. |
| Editar descripción | Añade (o edita) una descripción de texto para el panel. |
| Obtener vínculo del panel | Le permite dirigir a los usuarios a un panel concreto de un proyecto. Al hacer clic en el vínculo, el destinatario deberá iniciar sesión antes de que se le dirija al panel exacto al que está vinculado. |
