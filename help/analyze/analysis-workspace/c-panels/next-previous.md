---
description: Panel que muestra los elementos de dimensión siguientes o anteriores para una dimensión específica.
title: Panel de elementos siguiente o anterior
feature: Panels
role: User, Admin
source-git-commit: 2a16410a1a9ece301844ef0f242d09e3a16318c0
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 7%

---


# Panel de elementos siguiente o anterior

La variable [!UICONTROL Elemento siguiente o anterior] El panel se inició como un informe en Reports &amp; Analytics, en [!UICONTROL Informes] > [!UICONTROL Más popular] > [!UICONTROL Página siguiente/Página anterior]. Este panel de Workspace contiene varias tablas y visualizaciones para identificar fácilmente el elemento de dimensión siguiente o anterior para una dimensión específica. Por ejemplo,

## Acceso al panel

Puede acceder al panel desde [!UICONTROL Informes] o dentro de [!UICONTROL Espacio de trabajo].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está colapsado.</li><li>Si ha seleccionado [!UICONTROL Página siguiente], ya se ha aplicado la configuración predeterminada, como [!UICONTROL Página] para [!UICONTROL Dimension]y la página superior como el [!UICONTROL Elemento Dimension], [!UICONTROL Siguiente] para [!UICONTROL Dirección] y [!UICONTROL Visita] para [!UICONTROL Contenedor]. Puede modificar todos estos ajustes.</li></ul>![Panel siguiente/anterior](assets/next-previous.png) |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. A continuación, arrastre el [!UICONTROL Elemento siguiente o anterior] sobre la tabla improvisada. Observe que la variable [!UICONTROL Dimension] y [!UICONTROL Elemento Dimension] se dejan en blanco. Seleccione una dimensión en la lista desplegable. [!UICONTROL elementos del Dimension] se rellenan en función de la variable [!UICONTROL dimensión] usted eligió. Se agrega el elemento de dimensión superior, pero puede seleccionar otro elemento.<p>![Panel siguiente/anterior](assets/next-previous2.png) |

## Entradas de panel {#Input}

Puede configurar la variable [!UICONTROL Elemento siguiente o anterior] panel de panel con esta configuración de entrada:

| Configuración | Descripción |
| --- | --- |
| Zona de colocación de segmentos (u otros componentes) | Puede arrastrar y soltar segmentos u otros componentes para filtrar aún más los resultados del panel. |
| Dimensión | Dimensión para la que desea explorar elementos anteriores o siguientes. |
| Elemento de dimensión | El elemento |
| Dirección | Especifique si está buscando la variable [!UICONTROL Siguiente] o [!UICONTROL Anterior] elemento de dimensión. |
| Contenedor | [!UICONTROL Visita] o [!UICONTROL Visitante] (predeterminado) determina el ámbito de la consulta. |

Haga clic en **[!UICONTROL Generar]** para crear el panel.

## Salida de panel {#output}

La variable [!UICONTROL Elemento siguiente o anterior] devuelve un completo conjunto de datos y visualizaciones para ayudarle a comprender mejor qué ocurrencias siguen o preceden a elementos de dimensión específicos.

![Salida de panel siguiente/anterior](assets/next-previous-output.png)

![Salida de panel siguiente/anterior](assets/next-previous-output2.png)

