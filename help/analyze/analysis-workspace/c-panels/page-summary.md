---
description: Aprenda a utilizar el panel de resumen de página para mostrar la información de resumen de una página seleccionada.
title: Panel de resumen de página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
TQID: https://experienceleague.adobe.com/WI5opV6DcvJRF--HuX8PJcJd7G-3XU0-E0hWvvdlwmM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 642
ht-degree: 87%

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
>abstract="Revise rápidamente algunas de las métricas de alto nivel, así como el movimiento hacia una página específica y desde esta.<br/><br/>**Parámetros **<br/>**Añadir un elemento de dimensión de página**: abra el carril del componente, busque la dimensión Página y expándala haciendo clic en la zanahoria para ver los elementos de dimensión. A continuación, arrastre y suelte la página específica sobre la que desee obtener información en el generador. Una vez que haya arrastrado y soltado el elemento de dimensión, el informe se rellenará automáticamente con información clave sobre la página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta el panel Resumen de página en_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_No hay un panel equivalente en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Un panel **[!UICONTROL Resumen de página]** le permite explorar estadísticas clave sobre páginas específicas.

## Usar

Para usar un panel **[!UICONTROL Resumen de página]**:

1. Crear un panel de **[!UICONTROL Resumen de página]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.



Puede acceder al panel desde [!UICONTROL Informes] o desde [!UICONTROL Workspace].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está contraído.</li><li>Solo se admite la dimensión Página.</li><li>Ya se ha aplicado una configuración predeterminada, en este caso, la página más visitada para la dimensión [!UICONTROL Página]. Puede modificar esta configuración.</li></ul> |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. Arrastre el panel [!UICONTROL Resumen de página] sobre la tabla de forma libre. Observe que el [!UICONTROL Elemento de dimensión] de página se deja en blanco. Seleccione un elemento de dimensión en la lista desplegable. |

### Entrada de panel {#panel-input}

Puede configurar el panel [!UICONTROL Resumen de página] utilizando estos ajustes de entrada:

![Resumen de entrada de página](assets/page-summary-input.png)

| Entrada | Descripción |
| --- | --- |
| **[!UICONTROL Página]** | Seleccione una dimensión de página para la que desee explorar estadísticas clave. Por ejemplo, **[!UICONTROL inicio]** para explorar las estadísticas de la página de inicio. Utilice el menú desplegable para seleccionar una página o empiece a escribir (por ejemplo, `home`) para buscar páginas rápidamente. |

{style="table-layout:auto"}


Seleccione **[!UICONTROL Generar]** para generar el panel.

### Salida del panel {#panel-output}

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
