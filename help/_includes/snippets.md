---
source-git-commit: 33ac467cd73e3099ce0ca03aa41cbd4192eb2384
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 96%

---
# Fragmentos

## Anuncio del final de la vida útil de Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>A partir del **17 de enero de 2024**, el Adobe dejó de usar Reports &amp; Analytics y los informes y funciones que lo acompañaban. En ese momento, Reports &amp; Analytics y todos sus informes y programaciones dejaron de funcionar. Los informes, las visualizaciones y la tecnología subyacente que alimentan Reports &amp; Analytics ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de Reports &amp; Analytics están disponibles en Analysis Workspace. Para obtener información sobre el uso de informes en Analysis Workspace, consulte [Usar informes pregenerados](/help/analyze/analysis-workspace/reports/use-reports.md).
> 
>Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de Reports &amp; Analytics se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. Este aviso explica el proceso de finalización de la vida útil.
>
>Más información acerca del [Anuncio del final de la vida útil](https://www.adobe.com/go/analytics_rnaeol_es) de Reports &amp; Analytics.

## Criterios de filtro del diccionario de datos {#dd-filter-criteria}

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
| [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
| [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
| [!UICONTROL **Segmentos**] | Mostrar solo los componentes que son segmentos. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
| [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
| [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
| [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
| [!UICONTROL **Mostrar duplicados**] | <p>Mostrar solo los componentes que tengan el mismo nombre o definición que otro componente en el grupo de informes seleccionado. Los nombres o definiciones deben coincidir de forma exacta para que se muestren como duplicados.</p><p>Esta opción solo está disponible para administradores.</p><p>**NOTA:** Para las definiciones, esto incluye los componentes que crea, así como los proporcionados por Adobe. En el caso de los nombres, en este momento solo se incluyen los componentes que crea y no los proporcionados por Adobe. En una futura versión se agregará la posibilidad de mostrar los nombres duplicados de los componentes proporcionados por Adobe.</p> |
| [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
| [!UICONTROL **Creado por el Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

{style="table-layout:auto"}

## Información del componente del diccionario de datos {#dd-component-information}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Una vez aprobado el componente, los administradores pueden quitar la aprobación al seleccionar el botón **Aprobado**.</p> |
| [!UICONTROL **Aprobación necesaria**] | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para [!UICONTROL **Aprobar**]. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
| [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md)). |
| [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique primero el filtro **Mostrar todo** para asegurarse de que no está viendo componentes que no se hayan compartido con usted.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similar a**] | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se muestra cualquier componente duplicado del grupo de informes. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique primero el filtro **Mostrar todo** para asegurarse de que no está viendo componentes que no se hayan compartido con usted.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
| [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
| [!UICONTROL **Tipo de componente**] | Muestra el tipo de componente que es, ya sea una dimensión, una métrica, un segmento o un intervalo de fecha. |
| [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
| [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
| [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver segmentos, métricas calculadas e intervalos de fechas. |

{style="table-layout:auto"}

## Opciones de ordenación de componentes {#components-sort-options}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Recomendado**] | Ordena los componentes con los recomendados en la parte superior de la lista. Los componentes que usted u otras personas de su organización utilizan con más frecuencia y más recientemente aparecen en la parte superior de la lista. |
| [!UICONTROL **Alfabético**] | Ordena los componentes alfabéticamente. |
| [!UICONTROL **Categórica**] | Ordena los componentes según su tipo (dimensión, métrica, segmento, intervalo de fecha). |

{style="table-layout:auto"}

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).


## Aviso sobre complementos {#plug-in}

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el equipo de cuentas de Adobe de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

