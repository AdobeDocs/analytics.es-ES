---
source-git-commit: a53f7254d13dcb0858942dd9d295d8597d265ff8
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 64%

---
# Fragmentos

## Anuncio del final de la vida útil de Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>Más información acerca del [Anuncio del final de la vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics.

## Criterios de filtro del diccionario de datos {#dd-filter-criteria}

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que están en su lista de Favoritos. Para obtener información sobre cómo agregar componentes a la lista de favoritos, consulte [Resumen de componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Segmentos**] | Mostrar solo los componentes que son segmentos. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobados por un administrador. Como administrador, esto resulta útil a la hora de identificar componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Mostrar duplicados**] | <p>Mostrar solo los componentes que tienen la misma etiqueta o la misma definición que otro componente del grupo de informes seleccionado. Las etiquetas o definiciones deben coincidir de forma exacta para mostrarse como duplicados.</p><p>Esta opción solo está disponible para administradores.</p><p>**NOTA:** En el caso de las definiciones, esto incluye tanto los componentes que crea como los que proporciona Adobe. En el caso de las etiquetas, actualmente solo incluye los componentes que crea y no los que proporciona Adobe. En una versión futura se añadirán las etiquetas duplicadas para los componentes proporcionados por el Adobe.</p> |
   | [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Creado por Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

## Información del componente del diccionario de datos {#dd-component-information}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | <p>Indica que el administrador ha revisado y aprobado el componente.</p><p>Una vez aprobado un componente, los administradores pueden eliminar la aprobación seleccionando la **Aprobado** botón.</p> |
| [!UICONTROL **Aprobación necesaria**] | <p>Indica que el administrador aún no ha revisado ni aprobado el componente.</p><p>Los administradores ven una opción para lo siguiente [!UICONTROL **Aprobar**]. Al seleccionar esta opción, se marca el componente como &quot;Aprobado&quot; para los usuarios.</p> |
| [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md)). |
| [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en la [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**] campos desplegables. Antes de depurar los componentes que ven los usuarios, aplique primero el **Mostrar todo** filtre para asegurarse de que está viendo cualquier componente que no se haya compartido con usted y que otro administrador pueda haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similar a**] | <p>Muestra componentes con etiquetas similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: métrica, métrica calculada, dimensión, segmento e intervalo de fecha.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí también se muestra cualquier componente duplicado del grupo de informes. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en la [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**] campos desplegables. Antes de depurar los componentes que ven los usuarios, aplique primero el **Mostrar todo** filtre para asegurarse de que está viendo cualquier componente que no se haya compartido con usted y que otro administrador pueda haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** Actualmente, la variable **Similar a** Esta sección incluye solo los componentes que crea y no los que proporciona Adobe. En una versión futura se añadirán componentes proporcionados por el Adobe.</p> |
| [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
| [!UICONTROL **Tipo de componente**] | Muestra el tipo de componente que es, ya sea una dimensión, una métrica, un segmento o un intervalo de fecha. |
| [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
| [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
| [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver segmentos, métricas calculadas e intervalos de fechas. |

{style="table-layout:auto"}

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de lanzamiento de Analytics, consulte [Lanzamientos de funciones de Adobe Analytics](/help/release-notes/releases.md).


## Descargo de responsabilidad de complemento {#plug-in}

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el equipo de cuenta de Adobe de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

