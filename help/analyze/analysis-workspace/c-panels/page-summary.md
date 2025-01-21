---
description: El panel Resumen de página muestra información de resumen de una página de su elección.
title: Panel Resumen de página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 12%

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
>abstract="Revise rápidamente algunas de las métricas de alto nivel, así como el movimiento desde y hacia una página específica.<br/><br/>**Parámetros **<br/>**Agregar un elemento de dimensión de página**: abra el carril del componente, busque la dimensión Página y expanda la dimensión haciendo clic en la zanahoria para ver los elementos de dimensión. A continuación, arrastre y suelte la página específica sobre la que desee obtener información en el generador. Una vez que haya arrastrado y soltado el elemento de dimensión, el informe se rellena automáticamente con información clave sobre la página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta el panel Resumen de página en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_No hay un panel equivalente en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Un panel **[!UICONTROL Resumen de página]** le permite explorar estadísticas clave sobre páginas específicas.

## Utiliza

Para usar un panel **[!UICONTROL Resumen de página]**:

1. Crear un panel de **[!UICONTROL resumen de página]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.



Puede acceder al panel desde [!UICONTROL Informes] o desde [!UICONTROL Workspace].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está contraído.</li><li>Solo se admite la dimensión Página.</li><li>Ya se ha aplicado una configuración predeterminada, en este caso, la página más visitada para la dimensión [!UICONTROL Página]. Puede modificar esta configuración.</li></ul> |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. Arrastre el panel [!UICONTROL Resumen de página] sobre la tabla de forma libre. Observe que el campo Página [!UICONTROL Elemento de Dimension] se deja en blanco. Seleccione un elemento de dimensión en la lista desplegable. |

### Entrada de panel {#panel-input}

Puede configurar el panel [!UICONTROL Resumen de página] con esta configuración de entrada:

![Resumen de entrada de página](assets/page-summary-input.png)

| Entrada | Descripción |
| --- | --- |
| **[!UICONTROL Activity Map]** | Seleccione una dimensión de página para la que desee explorar estadísticas clave. |

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
| **[!UICONTROL Tendencia]** | Una visualización de tendencias [Línea](/help/analyze/analysis-workspace/visualizations/line.md) para las vistas de página de este mes, cuatro semanas antes y cincuenta y dos semanas antes. |
| **[!UICONTROL Porcentaje de todas las vistas de página]** | Un número de resumen para el porcentaje de todas las vistas de página que fueron a esta página. |
| **[!UICONTROL Tiempo invertido en la página]** | Una visualización de [barras horizontales](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) que muestra el tiempo empleado en esta página. |
| **[!UICONTROL Visitas de página única]** | [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de vistas de página donde esta página fue la única página visitada. |
| **[!UICONTROL Recargas]** | [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador. |
| **[!UICONTROL Entradas]** | [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un elemento determinado se captura como el primer valor de una visita. |
| **[!UICONTROL Salidas]** | [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra el número de veces que un elemento determinado se captura como el último valor de una visita. |
| **[!UICONTROL Flujo]** | Una visualización [Flow](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) con la página seleccionada como punto focal. Puede explorar en profundidad los datos como en cualquier visualización de [Flujo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar y reconstruir el panel.
