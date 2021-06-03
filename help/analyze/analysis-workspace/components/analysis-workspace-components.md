---
description: 'Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y rangos de tiempo que puede arrastrar y soltar en un proyecto. '
title: Resumen de componentes
feature: Conceptos básicos de Workspace
role: Business Practitioner, Administrator
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 92%

---

# Resumen de componentes

Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y rangos de tiempo que puede arrastrar y soltar en un proyecto.

Para acceder al panel Componentes, haga clic en el icono **[!UICONTROL Componentes]** en el carril izquierdo. Puede alternar entre [Paneles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es), [Visualizaciones](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=es) y Componentes desde los iconos del carril izquierdo o utilizando [teclas de acceso directo](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

También puede ajustar la [Configuración de vista de densidad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=es) del proyecto para ver más valores en el carril izquierdo a la vez. Para ello, vaya a **[!UICONTROL Proyecto > Información y configuración del proyecto > Vista de densidad]**.

## Dimensiones {#dimensions}

Las [**dimensiones**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html) son atributos de texto que describen el comportamiento de los visitantes y que se pueden ver, desglosar y comparar en el análisis. Se pueden encontrar en el carril izquierdo del componente (sección naranja) y se aplican normalmente como filas de una tabla.

Algunos ejemplos de dimensiones son [!UICONTROL Nombre de página], [!UICONTROL Canales de marketing], [!UICONTROL Tipo de dispositivo] y [!UICONTROL Productos]. Las dimensiones las proporciona Adobe y se capturan mediante su implementación personalizada (eVar, props, clasificaciones, etc.).

Cada dimensión también contiene **elementos de dimensión** dentro de ella. Para encontrar los elementos de dimensión en el carril izquierdo del componente, haga clic en la flecha derecha junto al nombre de cualquier dimensión (los elementos son amarillos).

Algunos ejemplos de elementos de dimensión son [!UICONTROL Página principal] (en la dimensión [!UICONTROL Página]), [!UICONTROL Búsqueda de pago] (en la dimensión [!UICONTROL Canal de marketing]), [!UICONTROL Tableta] (en la dimensión [!UICONTROL Tipo de dispositivo móvil]), etc.

![](assets/dimensions.png)

## Métricas {#metrics}

Las [**métricas**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html) son medidas cuantitativas acerca del comportamiento de los visitantes. Se pueden encontrar en el carril izquierdo del componente (sección verde) y se aplican normalmente como columnas de una tabla.

Algunos ejemplos de métricas son [!UICONTROL Vistas de página], [!UICONTROL Visitas], [!UICONTROL Pedidos], [!UICONTROL Tiempo promedio empleado] e [!UICONTROL Ingresos/Pedido]. Las métricas las proporciona Adobe o se capturan mediante la implementación personalizada ([!UICONTROL Eventos de éxito]), o se crean con el [Creador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segmentos {#segments}

Los [**segmentos**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) son filtros de audiencia que se aplican al análisis. Se pueden encontrar en el carril izquierdo del componente (sección azul) y se suelen aplicar en la parte superior de un panel o en columnas de métricas superiores de una tabla.

Algunos ejemplos de segmentos son [!UICONTROL Visitantes de dispositivos móviles], [!UICONTROL Visitas desde correo electrónico] y [!UICONTROL Visitas autenticadas]. Los segmentos los proporciona Adobe, o se crean en la [zona desplegable del panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) o con el [Generador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Intervalos de fechas {#date-ranges}

Los [**intervalos de fechas**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) son el intervalo de fechas en el que realiza el análisis. Se encuentran en el carril izquierdo del componente (sección morada) y se aplican normalmente en el calendario de cada panel.

Algunos ejemplos de intervalos de fechas son julio de 2019, [!UICONTROL Últimas 4 semanas] y [!UICONTROL Este mes]. Los intervalos de fechas los proporciona Adobe, se aplican en el [calendario del panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) o se crean con el [Generador de intervalos de fechas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)

## Acciones de componente {#actions}

Puede administrar componentes (de forma individual o seleccionando más de uno) directamente en el carril izquierdo. Haga clic con el botón secundario en un componente o haga clic en el icono de puntos Acción en la parte superior de la lista de componentes.

![](assets/component-actions.png)

| Acción de componente | Descripción |
|--- |--- |
| Etiqueta | Organizar o administrar componentes aplicándoles etiquetas. A continuación, puede buscar por etiqueta en el carril izquierdo haciendo clic en el filtro o escribiendo #. Las etiquetas también actúan como filtros en los administradores de componentes. |
| Favorito | Añadir el componente a la lista de favoritos. Al igual que las etiquetas, puede buscar por Favoritos en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
| Aprobar | Marque los componentes como aprobados para indicar a los usuarios que el componente lo ha aprobado la organización. Al igual que las etiquetas, puede buscar por Aprobado en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
| Compartir | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |
| Eliminar | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).
