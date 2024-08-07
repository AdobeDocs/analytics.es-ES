---
description: El panel Resumen de página muestra información de resumen de una página de su elección.
title: Panel Resumen de página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 9%

---

# Panel Resumen de página

Este panel le permite explorar fácilmente las estadísticas clave sobre páginas específicas.

## Acceso al panel

Puede acceder al panel desde [!UICONTROL Informes] o desde [!UICONTROL Workspace].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está contraído.</li><li>Solo se admite la dimensión Página.</li><li>Ya se ha aplicado una configuración predeterminada, en este caso la página más visitada para la dimensión [!UICONTROL Página]. Puede modificar esta configuración.</li></ul> |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. Arrastre el panel [!UICONTROL Resumen de página] sobre la tabla de forma libre. Observe que el campo Página [!UICONTROL Elemento de Dimension] se deja en blanco. Seleccione un elemento de dimensión en la lista desplegable. |

## Entradas de panel {#Input}

Puede configurar el panel [!UICONTROL Resumen de página] con esta configuración de entrada:

| Configuración | Descripción |
| --- | --- |
| Zona de colocación de segmentos (u otro componente) | Puede arrastrar y soltar segmentos u otros componentes para filtrar aún más los resultados del panel. |
| Elemento de dimensión de página | En la lista desplegable, seleccione el elemento de dimensión Página cuyas estadísticas clave desee explorar. |

{style="table-layout:auto"}

Haga clic en **[!UICONTROL Generar]** para generar el panel.

## Salida de panel {#output}

El panel [!UICONTROL Resumen de página] devuelve un completo conjunto de datos de métricas y visualizaciones para ayudarle a comprender mejor las estadísticas sobre páginas específicas.

| Métrica/Visualización | Descripción |
| --- | --- |
| [!UICONTROL Vistas de página] - Mes actual, hasta el momento | Número de vistas de página de esta página en el mes actual. |
| [!UICONTROL Vistas de página] - 4 semanas antes | Número de vistas de página de esta página durante el último mes. |
| [!UICONTROL Vistas de página] - 52 semanas antes | Número de vistas de página de esta página durante el último año. |
| [!UICONTROL Tendencia] | Gráfico de vista de página de tendencias de este mes, 4 semanas antes y 52 semanas antes. |
| [!UICONTROL Porcentaje de todas las vistas de página] | Un número de resumen para el porcentaje de todas las vistas de página que fueron a esta página. |
| [!UICONTROL Tiempo invertido en la página] | Gráfico de barras horizontales que enumera el tiempo empleado en esta página. |
| [!UICONTROL Visitas de página única] | Un número de resumen que enumera el número de vistas de página donde esta fue la única página visitada. |
| [!UICONTROL Recargas] | La métrica [!UICONTROL Recargas] muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador. |
| [!UICONTROL Entradas] | La métrica [!UICONTROL Entradas] muestra el número de veces que un elemento determinado se captura como el primer valor de una visita. |
| [!UICONTROL Salidas] | La métrica [!UICONTROL Salidas] muestra el número de veces que un elemento determinado se captura como el último valor de una visita. |
| [!UICONTROL Flujo] | Diagrama de flujo con la página seleccionada como punto focal. Puede explorar en profundidad los datos como en cualquier [diagrama de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

![Panel Resumen de página](assets/page-sum1.png)

![Métricas y flujo](assets/page-sum2.png)
