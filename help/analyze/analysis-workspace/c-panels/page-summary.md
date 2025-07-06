---
description: Aprenda a utilizar el panel de resumen de página para mostrar la información de resumen de una página seleccionada.
title: Panel de resumen de página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 96%

---

# Panel Resumen de página {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Resumen de página"
>abstract="Revise rápidamente algunas de las métricas de alto nivel, así como el movimiento desde y hacia una página específica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Panel Resumen de página"
>abstract="Revise rápidamente algunas de las métricas de alto nivel, así como el movimiento desde y hacia una página específica.<br/><br/>**Parámetros &#x200B;**<br/>**Añadir un elemento de dimensión de página**: abra el carril del componente, busque la dimensión Página y expándala haciendo clic en la zanahoria para ver los elementos de dimensión. A continuación, arrastre y suelte la página específica sobre la que desee obtener información en el generador. Una vez que haya arrastrado y soltado el elemento de dimensión, el informe se rellenará automáticamente con información clave sobre la página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta el panel Resumen de página en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_No hay un panel equivalente en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Un panel **[!UICONTROL Resumen de página]** le permite explorar estadísticas clave sobre páginas específicas.

## Usar

Para usar un panel **[!UICONTROL Resumen de página]**:

1. Crear un panel de **[!UICONTROL Resumen de página]**. Para obtener información sobre cómo crear un panel, consulte [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.



Puede acceder al panel desde [!UICONTROL Informes] o desde [!UICONTROL Workspace].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está contraído.</li><li>Solo se admite la dimensión Página.</li><li>Ya se ha aplicado una configuración predeterminada, en este caso, la página más visitada para la dimensión [!UICONTROL Página]. Puede modificar esta configuración.</li></ul> |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. Arrastre el panel [!UICONTROL Resumen de página] sobre la tabla de forma libre. Observe que el [!UICONTROL Elemento de dimensión] de página se deja en blanco. Seleccione un elemento de dimensión en la lista desplegable.  |

### Entrada de panel {#panel-input}

Puede configurar el panel [!UICONTROL Resumen de página] utilizando estos ajustes de entrada:

![Resumen de entrada de página](assets/page-summary-input.png)

| Entrada | Descripción |
| --- | --- |
| **[!UICONTROL Página]** | Seleccione una dimensión de página para la página de la que desee explorar estadísticas clave. |

{style="table-layout:auto"}


Seleccione **[!UICONTROL Generar]** para generar el panel.

### Salida de panel {#panel-output}

El panel [!UICONTROL Resumen de página] devuelve un completo conjunto de datos de métricas y visualizaciones para ayudarle a comprender mejor las estadísticas sobre páginas específicas.

![Panel Resumen de página](assets/page-summary-output.png)

| Visualización | Descripción |
| --- | --- |
| **[!UICONTROL Vistas de página] - Mes actual (hasta ahora)** | Una visualización [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de vistas de página para esta página en el mes actual. |
| **[!UICONTROL Vistas de página] - 4 semanas antes** | Una visualización [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de vistas de página para esta página durante el último mes. |
| **[!UICONTROL Vistas de página] - 52 semanas antes** | Una visualización [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de vistas de página para esta página durante el último año. |
| **[!UICONTROL Tendencia]** | Una visualización de tendencias [Línea](/help/analyze/analysis-workspace/visualizations/line.md) para las vistas de página de este mes, 4 semanas antes y 52 semanas antes. |
| **[!UICONTROL Porcentaje de todas las vistas de página]** | Un número de resumen para el porcentaje de todas las vistas de página que fueron a esta página. |
| **[!UICONTROL Tiempo invertido en la página]** | Una visualización de [barras horizontales](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) que muestra el tiempo empleado en esta página. |
| **[!UICONTROL Visitas de una sola página]** | Un [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de vistas de página donde esta página fue la única página visitada. |
| **[!UICONTROL Recargas]** | Un [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. Un visitante que actualiza su explorador es la forma más común de activar una recarga. |
| **[!UICONTROL Entradas]** | Un [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un determinado elemento de dimensión se captura como primer valor en una visita. |
| **[!UICONTROL Salidas]** | Un [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un elemento de dimensión determinado se captura como último valor en una visita. |
| **[!UICONTROL Flujo]** | Una visualización de [Flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) con la página seleccionada como punto focal. Puede explorar en profundidad los datos como en cualquier visualización de [Flujo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar y regenerar el panel.
