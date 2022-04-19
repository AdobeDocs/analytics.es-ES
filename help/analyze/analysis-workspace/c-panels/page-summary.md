---
description: El panel de resumen de la página muestra información resumida de una página de su elección.
title: Panel de resumen de la página
feature: Panels
role: User, Admin
source-git-commit: 4bb950350d258b8d608f6d95d37d7d860e23ed2c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 9%

---


# Panel de resumen de la página

La variable [!UICONTROL Resumen de la página] El panel se inició como un informe en Reports &amp; Analytics, en Informes > Participación > Análisis de página > Resumen de página. Ahora también es un panel de Workspace. Este panel le permite explorar fácilmente estadísticas clave sobre páginas específicas.

## Acceso al panel

Puede acceder al panel desde [!UICONTROL Informes] o dentro de [!UICONTROL Espacio de trabajo].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está colapsado.</li><li>Solo se admite la dimensión Página .</li><li>Ya se ha aplicado una configuración predeterminada, en este caso la página más visitada para la variable[!UICONTROL Página] dimensión. Puede modificar esta configuración.</li></ul> |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. Arrastre el [!UICONTROL Resumen de la página] sobre la tabla improvisada. Observe que la página [!UICONTROL Elemento Dimension] se deja en blanco. Seleccione un elemento de dimensión en la lista desplegable. |

## Entradas de panel {#Input}

Puede configurar la variable [!UICONTROL Elemento siguiente o anterior] panel de panel con esta configuración de entrada:

| Configuración | Descripción |
| --- | --- |
| Zona de colocación de segmentos (u otros componentes) | Puede arrastrar y soltar segmentos u otros componentes para filtrar aún más los resultados del panel. |
| Elemento de dimensión de página | En la lista desplegable, seleccione el elemento de dimensión cuyas estadísticas clave desee explorar. |

{style=&quot;table-layout:auto&quot;}

Haga clic en **[!UICONTROL Generar]** para crear el panel.

## Salida de panel {#output}

La variable [!UICONTROL Resumen de la página] devuelve un completo conjunto de métricas, datos y visualizaciones para ayudarle a comprender mejor las estadísticas de páginas específicas.

| Métrica/visualización | Descripción |
| --- | --- |
| [!UICONTROL Vistas de página] - Mes actual, hasta ahora | Número de vistas de página de esta página para el mes actual. |
| [!UICONTROL Vistas de página] - 4 semanas antes | Número de vistas de página de esta página durante el último mes. |
| [!UICONTROL Vistas de página] - 52 semanas antes | Número de vistas de página de esta página durante el último año. |
| [!UICONTROL Tendencia] | Un gráfico de vista de página de tendencias para este mes, 4 semanas antes y 52 semanas antes. |
| [!UICONTROL Porcentaje de todas las vistas de la página] | Un número de resumen del porcentaje de todas las vistas de página que se enviaron a esta página. |
| [!UICONTROL Tiempo invertido en la página] | Un gráfico de barras horizontal que enumera el tiempo empleado en esta página. |
| [!UICONTROL Visitas de página única] | Número de resumen que indica el número de vistas de página en las que esta fue la única página visitada. |
| [!UICONTROL Recargas] | La variable [!UICONTROL Recargas] muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador. |
| [!UICONTROL Entradas] | La variable [!UICONTROL Entradas] muestra el número de veces que un elemento de dimensión determinado se captura como el primer valor de una visita. |
| [!UICONTROL Salidas] | La variable [!UICONTROL Salidas] muestra el número de veces que un elemento de dimensión determinado se captura como el último valor de una visita. |
| [!UICONTROL Flujo] | Diagrama de flujo con la página seleccionada como punto focal. Puede profundizar en los datos como en cualquier [Diagrama de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/creating-flow-report.md). |

{style=&quot;table-layout:auto&quot;}
