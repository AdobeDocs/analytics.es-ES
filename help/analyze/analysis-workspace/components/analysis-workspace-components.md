---
description: 'Los componentes de Analysis Workspace constan de dimensiones, métricas, segmentos e intervalos de fechas que puede arrastrar y soltar en un proyecto. '
title: Resumen de componentes
feature: Conceptos básicos de Workspace
role: Profesional empresarial, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 17%

---


# Resumen de componentes

Los componentes de Analysis Workspace constan de dimensiones, métricas, segmentos e intervalos de fechas que puede arrastrar y soltar en un proyecto.

Para acceder al menú Componentes, haga clic en el icono **[!UICONTROL Componentes]** en el carril izquierdo. Puede alternar entre [Paneles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=es-ES), [Visualizaciones](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) y Componentes desde los iconos del carril izquierdo o utilizando [teclas de acceso directo](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

También puede ajustar la [Ver configuración de densidad](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) del proyecto para ver más valores en el carril izquierdo a la vez. Para ello, vaya a **[!UICONTROL Proyecto > Información y configuración del proyecto > Ver densidad]**.

## Dimensiones {#dimensions}

[****](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) Las dimensiones son atributos de texto que describen el comportamiento del visitante y que se pueden ver, desglosar y comparar en el análisis. Se pueden encontrar en el carril izquierdo del componente (sección naranja) y se aplican normalmente como filas de una tabla.

Algunos ejemplos de dimensiones son [!UICONTROL Nombre de página], [!UICONTROL Canales de marketing], [!UICONTROL Tipo de dispositivo] y [!UICONTROL Productos]. Los Dimension se proporcionan mediante Adobe y se capturan mediante su implementación personalizada (eVar, props, clasificaciones, etc.).

Cada dimensión también contiene **elementos de dimensión** dentro de ella. Para encontrar los elementos del Dimension en el carril izquierdo del componente, haga clic en la flecha derecha junto al nombre de cualquier dimensión (los elementos son amarillos).

Algunos ejemplos de elementos de dimensión son [!UICONTROL Página principal] (dentro de la dimensión [!UICONTROL Página]), [!UICONTROL Búsqueda paga] (dentro de la dimensión [!UICONTROL Canal de marketing]), [!UICONTROL Tablet] (dentro de la dimensión [!UICONTROL Tipo de dispositivo móvil] ), etc.

![](assets/dimensions.png)

## Métricas {#metrics}

[****](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) Las métricas son medidas cuantitativas sobre el comportamiento de los visitantes. Se pueden encontrar en el carril izquierdo del componente (sección verde) y se aplican normalmente como columnas de una tabla.

Algunos ejemplos de métricas son [!UICONTROL Vistas de página], [!UICONTROL Visitas], [!UICONTROL Pedidos], [!UICONTROL Tiempo promedio empleado] y [!UICONTROL Ingresos/Pedido]. Las métricas se proporcionan por Adobe o se capturan mediante la implementación personalizada ([!UICONTROL Eventos de éxito]), o se crean mediante el [Creador de métricas calculadas](https://docs.adobe.com/content/help/es-ES/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segmentos {#segments}

[****](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) Los segmentos son filtros de audiencia que se aplican al análisis. Se pueden encontrar en el carril izquierdo del componente (sección azul) y se suelen aplicar en la parte superior de un panel o en columnas de métricas superiores de una tabla.

Algunos ejemplos de segmentos son [!UICONTROL Visitantes de dispositivos móviles], [!UICONTROL Visitas desde correo electrónico] y [!UICONTROL Visitas autenticadas]. Los segmentos se proporcionan mediante Adobe, o se crean en la [zona desplegable del panel](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html), o se crean mediante el [Generador de segmentos](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Intervalos de fechas {#date-ranges}

[**Los**](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) intervalos de fechas son el intervalo de fechas en el que realiza el análisis. Se encuentran en el carril izquierdo del componente (sección morada) y se aplican normalmente en el calendario de cada panel.

Algunos ejemplos de intervalos de fechas son julio de 2019, [!UICONTROL Últimas 4 semanas] y [!UICONTROL Este mes]. Los intervalos de fechas se proporcionan por Adobe, se aplican en el [calendario del panel](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) o se crean mediante el [Generador de intervalos de fechas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)

## Acciones de componente {#actions}

Puede administrar componentes (de forma individual o seleccionando más de uno) directamente en el carril izquierdo. Haga clic con el botón derecho en un componente o haga clic en el icono Punto de acción en la parte superior de la lista de componentes.

![](assets/component-actions.png)

| Acción de componente | Descripción |
|--- |--- |
| Etiqueta | Organizar o administrar componentes aplicándoles etiquetas. A continuación, puede buscar por etiqueta en el carril izquierdo haciendo clic en el filtro o escribiendo #. Las etiquetas también actúan como filtros en los administradores de componentes. |
| Favorito | Añadir el componente a la lista de favoritos. Al igual que las etiquetas , puede buscar por Favoritos en el carril izquierdo y filtrar por ellas en los administradores de componentes. |
| Aprobar | Marque los componentes como Aprobados para indicar a los usuarios que el componente está aprobado por la organización. Al igual que las etiquetas , puede buscar por Aprobado en el carril izquierdo y filtrar por ellas en los administradores de componentes. |
| Compartir | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |
| Eliminar | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).
