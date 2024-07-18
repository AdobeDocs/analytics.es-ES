---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Edición de entradas en el diccionario de datos
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 100%

---

# Edición de entradas de componentes en el diccionario de datos

Los administradores de Analytics pueden editar entradas de componentes en el diccionario de datos de un grupo de informes determinado. Todos los usuarios del grupo de informes pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono del **Diccionario de datos** en el carril izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que el grupo de informes correcto está seleccionado en el menú desplegable. De forma predeterminada, se muestra el grupo de informes en el que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

   El tipo de componente se puede identificar mediante colores e iconos. **Dimensiones** ![Los iconos de dimensión](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son naranjas, **Segmentos** ![Los iconos de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, **Intervalos de fechas** ![Los iconos de intervalos de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y **Métricas** ![Los iconos de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes. El icono de Adobe indica una plantilla de métrica calculada o un segmento, y el icono de la calculadora ![Icono Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicó una métrica calculada que creó un administrador de Analytics en su organización.

{{dd-filter-criteria}}

1. (Opcional) Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

   {{components-sort-options}}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

   {{dd-component-information}}

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para guardar los cambios.
