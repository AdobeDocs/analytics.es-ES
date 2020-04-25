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

Puede crear un proyecto de Analytics robusto basado en cualquier combinación de visualizaciones, componentes de informe y tablas de datos. Incorpora muchas de las características del generador de tablas de Ad Hoc Analysis en Analytics.

En Analysis Workspace, puede comparar y diseccionar datos de formas en las que anteriormente no era posible. Por ejemplo, configurar informes de clasificación y realizar cambios reiterados en las consultas de datos y, a continuación, acceder y manipular los valores en el nivel de informe.

La consulta va directamente al motor de búsqueda (puede realizar cambios en línea sin abrir otros informes para crear el análisis). Los resultados se devuelven de forma inmediata sin que se actualice el explorador.

## Página de lista de proyectos de Workspace  {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (si no ve esta opción, como en la captura de pantalla que aparece a continuación, significa que ya es su página de aterrizaje).

![](assets/sample-project.png)

La lista de proyectos de Workspace contiene la siguiente información:

| Elemento | Descripción |
|---|---|
| Proyecto  [Plantillas](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | Puede utilizar estas plantillas de proyecto rellenadas previamente tal cual, o puede adaptarlas a sus necesidades (mediante la adición o sustitución de métricas o visualizaciones, por ejemplo) y guardarlas con un nuevo nombre. |
| [Crear nuevo proyecto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | Haga clic en este vínculo para iniciar un proyecto nuevo desde cero. |
| Administrar proyectos | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| Ver tutoriales | Le permite acceder a los [vídeos en YouTube de Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Nombre | Nombre del proyecto de Workspace. |
| Creado por | Persona que ha creado el proyecto (usted mismo o alguien que haya compartido su proyecto). |
| Etiquetas | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Última modificación | Fecha y hora de última modificación del proyecto. |

## Info y configuración del proyecto {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** proporciona información a nivel de proyecto sobre el proyecto activo actualmente.

| Configuración | Descripción |
|---|---|
| Nombre del proyecto | Nombre proporcionado al proyecto. Puede hacer doble clic en el nombre para editarlo. |
| Creado por | Nombre del propietario del proyecto. |
| Última modificación | Fecha de la última modificación del proyecto. |
| Etiquetas | Enumera cualquier etiqueta aplicada a un proyecto para una ordenación por categorías más sencilla. También puede etiquetar proyectos mientras los guarda. View a project&#39;s tags on the Workspace Landing Page in the [!UICONTROL Tags] column. |
| Descripción | Una descripción es útil para aclarar el propósito de un proyecto. Puede hacer doble clic en la descripción para editarla. |
| Contar instancias repetidas en el proyecto | Especifica si las instancias repetidas se cuentan en los informes. Si hay varios valores secuenciales para una misma variable, puede contarlos como una o como varias instancias de la variable. |
| Esquema de colores de visualización | Puede cambiar el esquema de colores que se utiliza en Workspace eligiendo una opción de una paleta de colores distinta o creando una paleta propia. Esta función afecta a muchos elementos del Workspace, incluidas la mayoría de visualizaciones. |
| Ver densidad | Le permite ver más datos en la pantalla al reducir el margen vertical del carril izquierdo, las tablas de forma libre y las tablas de cohorte. |

## Menú Proyectos {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

El menú Proyectos principal tiene esta apariencia:

![](assets/new-project-menus.png)

Los submenús contienen las siguientes opciones.

>[!NOTE] Las opciones marcadas con un asterisco (*) solo se muestran con los proyectos **guardados**.

| Proyecto | Editar | Insertar | Componentes | Compartir | Ayuda |
|---|---|---|---|---|---|
| Nuevo | Deshacer | Nuevo panel | Nuevo segmento | Compartir proyecto | Vídeos |
| Open | Borrar | Nuevo panel improvisado | Nueva métrica | Obtener vínculo del proyecto* | Teclas de acceso directo  |
| Guardar | Borrar todo | Nuevo panel de comparación de segmentos | Nuevo intervalo de fechas | Enviar archivo ahora* | Foro de ayuda |
| Guardar como* |  | Nueva tabla improvisada | Nueva alerta | Enviar archivo según lo programado* |  |
| Establecer como página de aterrizaje* |  | Nueva línea | Actualizar componentes | Depurar datos de proyectos |  |
| Actualizar proyecto |  | Nueva barra |  |  |  |
| Descargar CSV |  |  |  |  |  |
| Descargar PDF* |  |  |  |  |  |
| Info y configuración del proyecto |  |  |  |  |  |

## Carril izquierdo  {#section_271295C26EC840ABB2A8E7EC0498B60E}

El carril izquierdo tiene tres iconos que le permiten acceder a paneles, [visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) y [componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) (dimensiones, métricas, segmentos e intervalos de fechas) con un clic:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. Para crear un **Panel de cohorte nuevo**, arrastre un Panel en blanco y una visualización de una Tabla de cohorte.
