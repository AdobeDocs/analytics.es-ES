---
description: Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y rangos de tiempo que puede arrastrar y soltar en un proyecto.
title: Resumen de componentes
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 100%

---

# Resumen de componentes

Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y rangos de tiempo que puede arrastrar y soltar en un proyecto.

Para acceder al panel Componentes, haga clic en el icono **[!UICONTROL Componentes]** en el carril izquierdo. Puede alternar entre [Paneles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es), [Visualizaciones](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=es) y Componentes desde los iconos del carril izquierdo o utilizando [teclas de acceso directo](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

También puede ajustar la [Configuración de vista de densidad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=es) del proyecto para ver más valores en el carril izquierdo a la vez. Para ello, vaya a **[!UICONTROL Proyecto > Información y configuración del proyecto > Vista de densidad]**.

## Dimensiones {#dimensions}

Las [**dimensiones**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=es) son atributos de texto que describen el comportamiento de los visitantes y que se pueden ver, desglosar y comparar en el análisis. Se pueden encontrar en el carril izquierdo del componente (sección naranja) y se aplican normalmente como filas de una tabla.

Algunos ejemplos de dimensiones son [!UICONTROL Nombre de página], [!UICONTROL Canales de marketing], [!UICONTROL Tipo de dispositivo] y [!UICONTROL Productos]. Las dimensiones las proporciona Adobe y se capturan mediante su implementación personalizada (eVar, props, clasificaciones, etc.).

Cada dimensión también contiene **elementos de dimensión** dentro de ella. Para encontrar los elementos de dimensión en el carril izquierdo del componente, haga clic en la flecha derecha junto al nombre de cualquier dimensión (los elementos son amarillos).

Algunos ejemplos de elementos de dimensión son [!UICONTROL Página principal] (en la dimensión [!UICONTROL Página]), [!UICONTROL Búsqueda de pago] (en la dimensión [!UICONTROL Canal de marketing]), [!UICONTROL Tableta] (en la dimensión [!UICONTROL Tipo de dispositivo móvil]), etc.

![](assets/dimensions.png)

## Métricas {#metrics}

Las [**métricas**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=es) son medidas cuantitativas acerca del comportamiento de los visitantes. Se pueden encontrar en el carril izquierdo del componente (sección verde) y se aplican normalmente como columnas de una tabla.

Algunos ejemplos de métricas son [!UICONTROL Vistas de página], [!UICONTROL Visitas], [!UICONTROL Pedidos], [!UICONTROL Tiempo promedio empleado] e [!UICONTROL Ingresos/Pedido]. Las métricas las proporciona Adobe o se capturan mediante la implementación personalizada ([!UICONTROL Eventos de éxito]), o se crean con el [Creador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=es).

![](assets/metrics.png)

## Segmentos {#segments}

Los [**segmentos**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=es) son filtros de audiencia que se aplican al análisis. Se pueden encontrar en el carril izquierdo del componente (sección azul) y se suelen aplicar en la parte superior de un panel o en columnas de métricas superiores de una tabla.

Algunos ejemplos de segmentos son [!UICONTROL Visitantes de dispositivos móviles], [!UICONTROL Visitas desde correo electrónico] y [!UICONTROL Visitas autenticadas]. Los segmentos los proporciona Adobe, o se crean en la [zona desplegable del panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es) o con el [Generador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=es).

![](assets/segments.png)

## Intervalos de fechas {#date-ranges}

Los [**intervalos de fechas**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=es) son el intervalo de fechas en el que realiza el análisis. Se encuentran en el carril izquierdo del componente (sección morada) y se aplican normalmente en el calendario de cada panel.

Puede hacer que los componentes de intervalo de fecha sean relativos al calendario del panel. Para obtener más información, consulte [Acerca de los intervalos de fecha relativos del panel](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).

Algunos ejemplos de intervalos de fechas son julio de 2019, [!UICONTROL Últimas 4 semanas] y [!UICONTROL Este mes]. Los intervalos de fechas los proporciona Adobe, se aplican en el [calendario del panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es) o se crean con el [Generador de intervalos de fechas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=es).

![](assets/date-ranges.png)


## Administrar componentes {#actions}

Puede administrar componentes directamente en el carril izquierdo.

1. Haga clic con el botón derecho en un componente.

   O

   Seleccione un componente y a continuación, seleccione el icono de **Acción** (tres puntos) en la parte superior de la lista de componentes.

   >[!TIP]
   >
   >   Para seleccionar varios componentes, mantenga pulsada la tecla Mayús o Comando (en Mac) o Ctrl (en Windows).


   ![](assets/component-actions.png)

   | Acción de componente | Descripción |
   |--- |--- |
   | [!UICONTROL **Etiqueta**] | Organizar o administrar componentes aplicándoles etiquetas. A continuación, puede buscar por etiqueta en el carril izquierdo haciendo clic en el filtro o escribiendo #. Las etiquetas también actúan como filtros en los administradores de componentes. |
   | [!UICONTROL **Favorito**] | Añadir el componente a la lista de favoritos. Al igual que las etiquetas, puede buscar por Favoritos en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
   | [!UICONTROL **Aprobar**] | Marque los componentes como aprobados para indicar a los usuarios que el componente lo ha aprobado la organización. Al igual que las etiquetas, puede buscar por Aprobado en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
   | [!UICONTROL **Compartir**] | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |
   | [!UICONTROL **Eliminar**] | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).

## Búsqueda, filtrado y ordenación de la lista de componentes

Puede buscar, filtrar y ordenar la lista de componentes en el carril izquierdo de Analysis Workspace para localizar rápidamente un componente en particular.

### Búsqueda en la lista de componentes

1. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

2. En el campo de búsqueda, empiece a escribir el nombre del componente que desea utilizar en el proyecto.

   El tipo de componente se puede identificar por el color y el icono. **Dimensiones** ![Los iconos de dimensión](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son naranjas, **Segmentos** ![Los iconos de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, **Intervalos de fechas** ![Los iconos de intervalos de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y **Métricas** ![Los iconos de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes. El icono de Adobe indica una plantilla de métricas calculadas o de segmentos y el icono de calculadora ![icono de Calculadora](assets/calculated-metric-icon-created.png) indica una métrica calculada creada por un administrador de Analytics de su organización.

3. Seleccione el componente cuando aparezca en la lista desplegable.

### Filtrado de la lista de componentes

1. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

2. Seleccione el icono de **Filtro** ![icono de Filtro del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg).

   O

   Escriba el símbolo de almohadilla (#) en el campo de búsqueda.

3. Seleccione cualquiera de las siguientes opciones de filtro para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. |
   | [!UICONTROL **Segmentos**] | Mostrar solo los componentes que son segmentos. <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |

4. (Opcional) Para perfeccionar aún más la lista, puede ordenarla, tal como se describe en [Ordenación de la lista de componentes](#sort-the-component-list).

### Ordenación de la lista de componentes

1. (Opcional) Aplique cualquier filtro a la lista de componentes, tal como se describe en [Filtrado de la lista de componentes](#filter-the-component-list).

2. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

3. Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

   {{components-sort-options}}
