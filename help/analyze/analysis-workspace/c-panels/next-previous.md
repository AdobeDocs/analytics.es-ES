---
description: Panel que muestra los elementos de dimensión siguientes o anteriores de una dimensión específica.
title: Panel de elemento siguiente o anterior
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 5%

---

# Panel de elemento siguiente o anterior

Este panel contiene varias tablas y visualizaciones para identificar fácilmente el elemento de dimensión siguiente o anterior para una dimensión específica. Por ejemplo, es posible que desee explorar a qué páginas fueron más a menudo los clientes después de visitar la página de inicio.

## Acceso al panel

Puede acceder al panel desde [!UICONTROL Informes] o desde [!UICONTROL Workspace].

| Punto de acceso | Descripción |
| --- | --- |
| [!UICONTROL Informes] | <ul><li>El panel ya se ha colocado en un proyecto.</li><li>El carril izquierdo está contraído.</li><li>Si seleccionó [!UICONTROL Página siguiente], ya se aplicó la configuración predeterminada, como [!UICONTROL Página] para [!UICONTROL Dimension], y la página superior como [!UICONTROL Elemento de Dimension], [!UICONTROL Siguiente] para [!UICONTROL Dirección] y [!UICONTROL Visita] para [!UICONTROL Contenedor]. Puede modificar todos estos ajustes.</li></ul>![Panel siguiente/anterior](assets/next-previous.png) |
| Workspace | Cree un nuevo proyecto y seleccione el icono Panel en el carril izquierdo. A continuación, arrastre el panel [!UICONTROL Elemento siguiente o anterior] sobre la tabla de forma libre. Observe que los campos [!UICONTROL Dimension] y [!UICONTROL Elemento de Dimension] se han dejado en blanco. Seleccione una dimensión de la lista desplegable. [!UICONTROL los elementos del Dimension] se rellenan en función de la [!UICONTROL dimensión] que haya elegido. Se agrega el elemento de dimensión principal, pero puede seleccionar otro elemento. Los valores predeterminados son Siguiente y Visitante. De nuevo, también puede modificarlos.<p>![Panel siguiente/anterior](assets/next-previous2.png) |

{style="table-layout:auto"}

## Entradas de panel {#Input}

Puede configurar el panel [!UICONTROL Elemento siguiente o anterior] con esta configuración de entrada:

| Configuración | Descripción |
| --- | --- |
| Zona de colocación de segmentos (u otro componente) | Puede arrastrar y soltar segmentos u otros componentes para filtrar aún más los resultados del panel. |
| Dimensión | Dimensión para la que desea explorar elementos siguientes o anteriores. |
| Elemento de dimensión | El artículo específico en el centro de su consulta siguiente/anterior. |
| Dirección | Especifique si está buscando el elemento de dimensión [!UICONTROL Siguiente] o [!UICONTROL Anterior]. |
| Contenedor | [!UICONTROL Visita] o [!UICONTROL Visitante] (predeterminado) determinan el ámbito de tu consulta. |

{style="table-layout:auto"}

Haga clic en **[!UICONTROL Generar]** para generar el panel.

## Salida de panel {#output}

El panel [!UICONTROL Elemento siguiente o anterior] devuelve un conjunto completo de datos y visualizaciones para ayudarle a comprender mejor qué ocurrencias siguen o preceden a elementos de dimensión específicos.

![Salida de panel siguiente/anterior](assets/next-previous-output.png)

![Salida de panel siguiente/anterior](assets/next-previous-output2.png)

| Visualización | Descripción |
| --- | --- |
| Barra horizontal | Enumera los elementos siguientes (o anteriores) en función del elemento de dimensión elegido. Al pasar el ratón por encima de una barra individual, se resalta el elemento correspondiente de la tabla de forma libre. |
| Número de resumen | Número de resumen de alto nivel de todas las ocurrencias de elementos de dimensión siguientes o anteriores para el mes actual (hasta ahora). |
| Tabla de forma libre | Enumera los elementos siguientes (o anteriores) en función del elemento de dimensión elegido, en formato de tabla. Por ejemplo, cuáles eran las páginas más populares (por ocurrencias) a las que se dirigían los visitantes después (o antes) de la página principal o de la página de Workspace. |

{style="table-layout:auto"}
