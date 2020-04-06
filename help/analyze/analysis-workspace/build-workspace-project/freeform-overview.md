---
description: 'null'
keywords: Analysis Workspace
title: 'Creación de un proyecto: Resumen'
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Creación de un proyecto: Resumen

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Puede crear un proyecto sólido de Analytics basado en cualquier combinación de visualizaciones, componentes de informes y tablas de datos. Incorpora muchas de las funciones del creador de tablas de la Análisis ad hoc en Analytics.

En Espacio de trabajo de Análisis, puede comparar y diseccionar datos de formas que antes no eran posibles. Por ejemplo, configure informes de clasificación, realice cambios iterativos inmediatos en la consulta de datos y, a continuación, acceda a los valores y los manipule en el nivel de sistema de informes.

La consulta va directamente al motor de sistema de informes; puede realizar cambios en línea sin que aparezcan otros informes para crear la análisis. Los resultados se devuelven inmediatamente, sin actualizar el explorador.

## Página de lista de proyectos de Workspace  {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (Si no ve esta opción, como en la captura de pantalla de abajo, ya es su página de aterrizaje).

![](assets/sample-project.png)

La página lista del proyecto de Workspace contiene la siguiente información:

| Elemento | Descripción |
|---|---|
| Proyecto  [Plantillas](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | Puede utilizar estas plantillas de proyecto rellenadas previamente tal como son o adaptarlas a sus necesidades (mediante la adición o sustitución de métricas o visualizaciones, por ejemplo) y guardarlas con un nuevo nombre. |
| [Crear nuevo proyecto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | Haga clic en este vínculo para inicio de un nuevo proyecto desde cero. |
| Administrar proyectos | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| Tutoriales de Vista | Le lleva a los vídeos [de YouTube de](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)Análisis Workspace. |
| Nombre | Nombre del proyecto de Workspace. |
| Creado por | La persona que creó este proyecto (usted o alguien que compartió el proyecto con usted). |
| Etiquetas | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Última modificación | Fecha y hora en que se modificó el proyecto por última vez. |

## Info y configuración del proyecto {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** proporciona información a nivel de proyecto sobre el proyecto activo actualmente.

| Configuración | Descripción |
|---|---|
| Nombre del proyecto | Nombre dado al proyecto. Puede hacer clic con el doble en el nombre para editarlo. |
| Creado por | Nombre del propietario del proyecto |
| Última modificación | Fecha de la última modificación del proyecto. |
| Etiquetas | Lista cualquier etiqueta aplicada a un proyecto para facilitar la categorización. También puede etiquetar proyectos al guardarlos. Vista de las etiquetas de un proyecto en la Página de aterrizaje Espacio de trabajo de la [!UICONTROL Tags] columna. |
| Descripción | Una descripción es útil para aclarar el propósito de un proyecto. Puede hacer clic con el doble en la descripción para editarla. |
| Contar instancias repetidas en el proyecto | Especifica si los casos repetidos se cuentan en los informes. Si tiene varios valores secuenciales para la misma variable, puede contarlos como una o como varias instancias de la variable. |
| Esquema de colores de visualización | Puede cambiar la combinación de colores utilizada en Workspace, eligiendo una paleta de colores diferente o especificando su propia paleta. Esta función afecta a muchos elementos del Workspace, incluidas la mayoría de visualizaciones. |
| Ver densidad | Le permite ver más datos en la pantalla al reducir el margen vertical del carril izquierdo, las tablas de forma libre y las tablas de cohorte. |

## Menú Proyectos {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

El menú Proyectos principal tiene este aspecto:

![](assets/new-project-menus.png)

Los submenús contienen las siguientes opciones.

>[!NOTE] Las opciones marcadas con un asterisco (*) solo se muestran con los proyectos **guardados**.

| Proyecto | Editar | Insertar | Componentes | Compartir | Ayuda |
|---|---|---|---|---|---|
| Nuevo | Deshacer | Nuevo panel | Nuevo segmento | Compartir proyecto | Vídeos |
| Open | Borrar | Nuevo panel improvisado | Nueva métrica | Obtener vínculo del proyecto* | Teclas de acceso directo  |
| Guardar | borrar todo | Nuevo panel de comparación de segmentos | Nuevo intervalo de fechas | Enviar archivo ahora* | Foro de ayuda |
| Guardar como* |  | Nueva tabla improvisada | Nueva alerta | Enviar archivo según lo programado* |  |
| Establecer como página de destino* |  | Nueva línea | Actualizar componentes | Depurar datos de proyectos |  |
| Actualizar proyecto |  | Nueva barra |  |  |  |
| Descargar CSV |  |  |  |  |  |
| Descargar archivo PDF* |  |  |  |  |  |
| Info y configuración del proyecto |  |  |  |  |  |

## Carril izquierdo  {#section_271295C26EC840ABB2A8E7EC0498B60E}

El carril izquierdo tiene tres iconos que le permiten acceder a paneles, [visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) y [componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) (dimensiones, métricas, segmentos e intervalos de fechas) con un clic:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. Para crear un **Panel de cohorte nuevo**, arrastre un Panel en blanco y una visualización de una Tabla de cohorte.
