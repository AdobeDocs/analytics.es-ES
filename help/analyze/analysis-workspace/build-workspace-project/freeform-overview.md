---
description: Obtenga información sobre los conceptos básicos de un proyecto de Workspace.
keywords: Analysis Workspace
title: Información general sobre Proyectos
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 08f3926bfa621ce3678da6db0f0a30ac5302b757
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 72%

---

# Información general sobre Proyectos

Los proyectos de Workspace le permiten combinar componentes, tablas y visualizaciones de datos para crear un análisis y compartirlo con cualquier persona de su organización. Antes de iniciar el primer proyecto, aprenda a acceder a sus proyectos, así como a navegar por ellos y a gestionarlos.

Aquí tiene un vídeo sobre cómo crear un proyecto de Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## Lista de proyectos {#project-list}

La primera vez que acceda a **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, la página muestra todos los proyectos que posee o a los que se le ha otorgado acceso. También es la página de aterrizaje de Adobe Analytics, a menos que haya establecido previamente una página de aterrizaje personalizada.

![](assets/sample-project.png)

La página Proyectos contiene la siguiente información:

>[!NOTE]
>
>Algunas columnas no se muestran de forma predeterminada. Para personalizar las columnas que ve, haga clic en **Personalizar tabla** icono ![Personalizar tabla](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg).


| Elemento | Descripción |
|---|---|
| [Editar preferencias](/help/analyze/analysis-workspace/user-preferences.md) | Administre la configuración de Analysis Workspace y sus componentes relacionados para todos los proyectos o paneles nuevos que cree. |
| [Crear carpeta](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Agregue una nueva carpeta o subcarpeta a la lista de proyectos y carpetas. |
| [Crear proyecto](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | Iniciar un nuevo proyecto desde cero o desde un informe. |
| Mostrar más | Muestra las opciones para crear un proyecto o un cuadro de resultados móvil en blanco. [ver tutoriales de formación](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=es), o [ver notas de la versión](/help/release-notes/latest.md). |
| Mostrar carpetas y proyectos | Elija si desea mostrar la estructura de carpetas de los proyectos. Para obtener más información, consulte [Acerca de las carpetas en Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Personalizar tabla (icono) | Permite personalizar la información que se muestra para cada proyecto en la página Proyectos. |
| Nombre | Nombre del proyecto de Workspace. |
| Tipo | Indica si se trata de un proyecto de Workspace, una carpeta o una [informe de valoración móvil](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=es). |
| Etiquetas | Etiquetas aplicadas al proyecto. |
| Programado | Indica si los proyectos están programados para enviarse por correo electrónico a los destinatarios según una programación. Consulte [Programar proyectos](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Vínculo compartido (cualquiera) | Los proyectos se pueden compartir con cualquier persona, incluso con personas que no tengan acceso a Analysis Workspace. Esta columna muestra si los proyectos se han compartido de esta manera. Consulte [Compartir un proyecto con cualquiera (no se requiere inicio de sesión)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Compartir proyectos](/help/analyze/analysis-workspace/curate-share/share-projects.md) para obtener más información. |
| Grupo de informes | Grupo de informes al que está asociado el proyecto. |
| [Función del proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=es) | Indica la función en el proyecto: propietarios, edición, duplicado o vista. |
| Propietario | Persona que ha creado el proyecto (usted mismo o alguien que haya compartido su proyecto). |
| Compartido con | Usuarios con los que se ha compartido el proyecto. |
| Última modificación | Fecha y hora de última modificación del proyecto. |
| Última apertura | Fecha y hora de última apertura del proyecto. |
| Identificador de proyecto | El ID del proyecto. |
| Intervalo de fecha más largo | Intervalo de fecha más largo del proyecto. |
| Cantidad de consultas | Número total de consultas contenidas en el proyecto. |
| Ubicación | Carpeta en la que reside el proyecto. |

## Barra de menú {#menu-bar}

En un proyecto, el menú proporciona opciones para administrar el proyecto, agregar componentes, buscar ayuda, etc. También se puede acceder a cada opción de menú mediante [métodos abreviados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=es) del teclado.

![](assets/menu.png)

| Elemento del menú | Descripción |
|---|---|
| Proyecto  | Incluye acciones comunes para la administración de proyectos, como Nuevo, Abrir, Guardar, Guardar como y [Guardar como informe de la empresa](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). También puede actualizar todo el proyecto para recuperar los datos y las definiciones más recientes haciendo clic en Actualizar proyecto. Las opciones [Descargar CSV y PDF](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es) permiten exportar datos desde Workspace. [Información y configuración del proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=es#info-settings) ofrece muchas opciones para administrar el proyecto. |
| Editar | Deshacer o volver a hacer la última acción. Borrar todo restablecerá el proyecto a un punto de partida en blanco. |
| Insertar | Inserte nuevos paneles o visualizaciones desde este menú. También puede insertar nuevos paneles y visualizaciones desde el carril izquierdo. |
| [Componentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=es) | Cree nuevos componentes de segmento, métrica calculada, intervalo de fecha o alerta a partir del proyecto. También puede crear nuevos componentes desde el carril izquierdo. Si las definiciones de los componentes han cambiado recientemente, Actualizar componentes recuperará las definiciones más recientes. |
| [Compartir](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html?lang=es) | Puede revisar, compartir y programar proyectos en PDF/CSV para destinatarios de su organización. |
| Ayuda | Acceda a la documentación de ayuda, los vídeos y la [comunidad de Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es) de Analytics. Administre la visibilidad de las sugerencias de Workspace, así como el [depurador](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Descubra información acerca de Workspace y factores que afectan al [rendimiento](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=es) del proyecto. |
| Botón Compartir o Propietario | Si se encuentra en Propio o Editar en el proyecto, el botón Compartir situado en la parte superior derecha le permite administrar los destinatarios del proyecto con un solo clic. Si tiene la función Duplicar o Ver en el proyecto, verá el nombre del propietario del proyecto. |

### Info y configuración del proyecto {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]** proporciona información a nivel de proyecto sobre el proyecto activo.

![](assets/projectinfo.png)

La configuración incluye lo siguiente:

| Configuración | Descripción |
|---|---|
| Nombre del proyecto | Nombre proporcionado al proyecto. Puede hacer doble clic en el nombre para editarlo. |
| Creado por | Nombre del propietario del proyecto. |
| Última modificación | Fecha de la última modificación del proyecto. |
| Etiquetas | Enumera cualquier etiqueta aplicada a un proyecto para una ordenación por categorías más sencilla. |
| Descripción | Una descripción es útil para aclarar el propósito de un proyecto. Puede hacer doble clic en la descripción para editarla. |
| Contar instancias repetidas en el proyecto | Especifica si las instancias repetidas se cuentan en los informes. Por ejemplo, esta configuración (cuando está activada) trata varias vistas de páginas consecutivas a la misma página como varias vistas de página. Con esta opción desactivada, se cuentan como una sola vista de página (esto solo afecta a ciertas métricas, como las visitas a una sola página). **Nota**: Esta configuración no se aplica a las visualizaciones de flujo o visitas en orden previsto. |
| [Paleta de colores del proyecto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=es) | Puede cambiar la paleta de colores categórica que se utiliza en Workspace eligiendo una de las paletas integradas que se han optimizado para casos de daltonismo o especificando la paleta personalizada. Esta función afecta a muchos elementos del Workspace, incluidas la mayoría de visualizaciones. |
| [Ver densidad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=es) | Le permite ver más datos en la pantalla al reducir el margen vertical del carril izquierdo, las tablas de forma libre y las tablas de cohorte. |

## Carril izquierdo {#left-rail}

Dentro de un proyecto, hay varios iconos disponibles en el carril izquierdo y cada uno representa partes importantes de un proyecto:

* [Paneles](/help/analyze/analysis-workspace/c-panels/panels.md) ![icono de paneles](assets/panels-icon.png)

* [Visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![icono de visualizaciones](assets/visualizations-icon.png)

* [Componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)![icono de componentes](assets/components-icon.png)

* [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)![icono del diccionario de datos](assets/data-dictionary-icon.png)

* [Tabla de contenido](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![icono de tabla de contenido](assets/toc-icon.png)

Los componentes (dimensiones, métricas, filtros e intervalos de fechas) del carril izquierdo están relacionados con la vista de datos del panel activo. El panel activo se identifica con el borde azul que lo rodea y la vista de datos activa se muestra en la parte superior del carril del componente.

![Los componentes relacionados con la vista de datos del panel activo para la vista de datos de demostración entre industrias.](assets/left-rail.png)



## Menú contextual

Aquí tiene un vídeo sobre el uso del menú de botón derecho en Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## Lienzo del proyecto {#canvas}

En el lienzo del proyecto se reúnen los paneles, las tablas, las visualizaciones y los componentes para generar el análisis. Un proyecto puede contener muchos paneles, y cada panel puede contener muchas tablas y visualizaciones.

Los paneles son útiles cuando desea organizar sus proyectos según períodos de tiempo, grupos de informes o casos de uso de análisis. El panel principal tiene un borde azul alrededor y determina qué componentes están disponibles en el carril izquierdo.

Según el punto de partida que haya elegido para sus proyectos, tendrá una [tabla de forma libre](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=es) o un [panel en blanco](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=es) en el lienzo para empezar. La forma más rápida de empezar a analizar es seleccionar uno o varios componentes y simplemente arrastrarlos y soltarlos en el lienzo del proyecto. Automáticamente, se mostrará una tabla de datos. [Obtenga más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=es) acerca de las diferentes opciones para crear una tabla o aproveche nuestros [tutoriales de aprendizaje](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es#training-tutorial) para obtener más información acerca de cómo crear su primer proyecto.

![](assets/canvas.png)

## Gestor de proyecto {#manager}

Los proyectos de Analysis Workspace se pueden administrar en **[!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos]**. El administrador de proyectos muestra los elementos que ha creado un usuario en particular.

La propiedad del proyecto se puede transferir a un nuevo usuario en [!UICONTROL Administración] > [!UICONTROL Usuarios y activos de Analytics] > [!UICONTROL Transferir activos].

En el administrador de proyectos, puede agregar, etiquetar, compartir, duplicar/copiar, etc. Busque un proyecto en la barra de búsqueda o utilizando las opciones de filtro del carril izquierdo. Puede filtrar por etiqueta, propietarios, tipo de proyecto y más.

![](assets/project-manager.png)

Las siguientes acciones comunes del administrador de proyectos se pueden llevar a cabo en uno o varios proyectos a la vez:

| Acción | Descripción |
|---|---|
| Agregar | Cree un nuevo proyecto desde cero o comience desde una [informe](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| Etiquetar o Aprobar | Elija &quot;Etiqueta&quot; o &quot;Aprobar&quot; para organizar sus proyectos y facilitar su búsqueda. |
| [Compartir](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=es) | Hace que este proyecto esté disponible para otros usuarios de Analysis Workspace de su organización. |
| Eliminar | Elimine el proyecto. |
| Cambiar nombre | Edite el nombre del proyecto. |
| Copiar | Cree un duplicado del proyecto. Esto crea un nuevo proyecto y un ID de proyecto. No se copiará ningún recurso compartido o programación vinculados al proyecto original. |
| Exportar a CSV | Descargue el proyecto como archivo CSV, que incluye datos de texto sin formato. |
