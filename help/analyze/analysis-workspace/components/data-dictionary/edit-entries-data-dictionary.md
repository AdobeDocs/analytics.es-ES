---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y realizar un seguimiento de los distintos componentes de Analysis Workspace, incluido su uso previsto, que se aprueba, que son duplicados, etc.
title: Edición de entradas en el diccionario de datos
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 85%

---

# Edición de entradas de componentes en el diccionario de datos

Los administradores de Analytics pueden editar entradas de componentes en el diccionario de datos de un grupo de informes determinado. Todos los usuarios del grupo de informes pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono del **Diccionario de datos** en el carril izquierdo de Analysis Workspace. (En [Acceso al diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary) se describen formas alternativas de obtener acceso al diccionario de datos.)

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que el grupo de informes correcto está seleccionado en el menú desplegable. De forma predeterminada, se muestra el grupo de informes en el que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

   El tipo de componente se puede identificar mediante colores e iconos. **Dimensiones** ![Los iconos de dimensión](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son naranjas, **Segmentos** ![Los iconos de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, **Intervalos de fechas** ![Los iconos de intervalos de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y **Métricas** ![Los iconos de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes. El icono de Adobe indica una plantilla de métrica calculada o un segmento, y el icono de la calculadora ![Icono Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicó una métrica calculada que creó un administrador de Analytics en su organización.

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | **[!UICONTROL Aprobado]** | Solo los componentes marcados como Aprobado por un administrador. |
   | **[!UICONTROL Favoritos]** | Solo los componentes que están en su lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | **[!UICONTROL Dimensiones]** | Solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña **[!UICONTROL Filtros rápidos]** al acceder por primera vez al diccionario de datos). |
   | **[!UICONTROL Métricas]** | Solo los componentes que son métricas. (Esta opción también está disponible en la pestaña **[!UICONTROL Filtros rápidos]** al acceder por primera vez al diccionario de datos). |
   | **[!UICONTROL Segmentos]** | Solo los componentes que son segmentos. (Esta opción también está disponible en la pestaña **[!UICONTROL Filtros rápidos]** al acceder por primera vez al diccionario de datos). |
   | **[!UICONTROL Intervalos de fechas]** | Solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña **[!UICONTROL Filtros rápidos]** al acceder por primera vez al diccionario de datos). |
   | **[!UICONTROL Mostrar todo]** | Todos los componentes. Esta opción solo está disponible para administradores. |
   | **[!UICONTROL No aprobado]** | Solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | **[!UICONTROL Falta la descripción]** | Solo los componentes que aún no tienen una descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | **[!UICONTROL Mostrar duplicados]** | <p>Solo los componentes que tienen el mismo nombre o la misma definición que otro componente del grupo de informes seleccionado. Los nombres o definiciones deben coincidir de forma exacta para que se muestren como duplicados.</p><p>Esta opción solo está disponible para administradores.</p><p>**NOTA:** Para las definiciones, esto incluye los componentes que crea, así como los proporcionados por Adobe. En el caso de los nombres, en este momento solo se incluyen los componentes que crea y no los proporcionados por Adobe. En una futura versión se agregará la posibilidad de mostrar los nombres duplicados de los componentes proporcionados por Adobe.</p> |
   | **[!UICONTROL No hay datos recientes]** | Solo los componentes que no han recopilado datos en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | **[!UICONTROL Creado por Adobe]** <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe.  Por ejemplo, Adobe Target. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

1. (Opcional) Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Recomendado**] | Ordena los componentes con los recomendados en la parte superior de la lista. Los componentes que usted u otras personas de su organización utilizan con más frecuencia y más recientemente aparecen en la parte superior de la lista. |
   | [!UICONTROL **Alfabético**] | Ordena los componentes alfabéticamente. |
   | [!UICONTROL **Categórica**] | Ordena los componentes según su tipo (dimensión, métrica, segmento, intervalo de fecha). |

   {style="table-layout:auto"}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

   | Opción | Función |
   |---------|----------|
   | **[!UICONTROL Aprobado]** | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Una vez aprobado el componente, los administradores pueden quitar la aprobación al seleccionar el botón **Aprobado**.</p> |
   | **[!UICONTROL Aprobación necesaria]** | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para **[!UICONTROL Aprobar]**. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
   | **[!UICONTROL Descripción]** | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md)). |
   | **[!UICONTROL Usado frecuentemente con]** | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables **[!UICONTROL Incluir siempre]** y **[!UICONTROL Excluir siempre]**. Antes de depurar los componentes que ven los usuarios, aplique primero el filtro **Mostrar todo** para asegurarse de que no está viendo componentes que no se hayan compartido con usted.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | **[!UICONTROL Similar a]** | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se muestra cualquier componente duplicado del grupo de informes. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables **[!UICONTROL Incluir siempre]** y **[!UICONTROL Excluir siempre]**. Antes de depurar los componentes que ven los usuarios, aplique primero el filtro **Mostrar todo** para asegurarse de que no está viendo componentes que no se hayan compartido con usted.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
   | **[!UICONTROL Etiquetas]** | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
   | **[!UICONTROL Tipo de componente]** | Muestra el tipo de componente que es, ya sea una dimensión, una métrica, un segmento o un intervalo de fecha. |
   | **[!UICONTROL Creado por]** | Muestra el nombre del usuario que ha creado el componente. |
   | **[!UICONTROL Vista previa]** | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
   | **[!UICONTROL Fecha de la última modificación]** | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver segmentos, métricas calculadas e intervalos de fechas. |

   {style="table-layout:auto"}

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para guardar los cambios.
