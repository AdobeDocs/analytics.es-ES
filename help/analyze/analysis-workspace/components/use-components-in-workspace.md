---
description: Obtenga información sobre cómo añadir componentes a un proyecto en Analysis Workspace
title: Uso de componentes en Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 16%

---

# Uso de componentes en Analysis Workspace

Los componentes constituyen los datos reales de cualquier proyecto de Analysis Workspace. Los componentes están formados por dimensiones, métricas, segmentos e intervalos de fechas. Puede añadir componentes a un proyecto arrastrándolos a visualizaciones o paneles.

Para obtener información general sobre los tipos de componentes que puede agregar, consulte [Resumen de componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>Para obtener información sobre cada componente, seleccione el icono de información junto al nombre de un componente en el carril izquierdo de Analysis Workspace o consulte la [Guía de componentes de Analytics](/help/components/home.md).

## Empezar a añadir componentes a un proyecto

1. [Creación de un proyecto en Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) si aún no lo ha hecho.

1. [Agregar un panel](/help/analyze/analysis-workspace/c-panels/panels.md) o [añadir una visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al proyecto en Analysis Workspace.

   Si agrega un componente a un proyecto en blanco, se crea automáticamente una visualización de tabla de forma libre.

1. Seleccione el icono **[!UICONTROL Componentes]** en el carril izquierdo.

   ![](assets/build-components.png)

1. Desplácese hasta el componente que desee añadir o búsquelo y, a continuación, arrástrelo hasta un panel o visualización del proyecto.

1. (Opcional) Arrastre un componente a la zona de colocación de segmentos en el encabezado de un panel.

   Los segmentos se aplican a todo el contenido del panel.

   Para obtener información sobre cómo puede utilizar la zona de colocación de segmentos en un panel para filtrar el panel, consulte [Zona de colocación](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Información general de paneles](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![colocar un segmento en la zona de colocación](assets/segment-dropzone.png)

1. Para obtener información más detallada, continúe con una de las siguientes secciones, según el tipo de componente que esté agregando:

   * [Adición de dimensiones a un proyecto](#add-dimensions-to-a-project)

   * [Agregar métricas a un proyecto](#add-metrics-to-a-project)

   * [Añadir segmentos a un proyecto](#add-segments-to-a-project)

   * [Adición de intervalos de fechas a un proyecto](#add-date-ranges-to-a-project)

## Adición de dimensiones a un proyecto

[Dimension](/help/components/dimensions/overview.md) son variables en Adobe Analytics que generalmente contienen valores de cadena. Las dimensiones comunes incluyen [Página](/help/components/dimensions/page.md), [Dominio de referencia](/help/components/dimensions/referring-domain.md) o una [eVar](/help/components/dimensions/evar.md). Por el contrario, las [métricas](/help/components/metrics/overview.md) contienen valores numéricos que se vinculan a una dimensión. Un informe básico muestra filas de valores de cadena (dimensión) frente a una columna de valores numéricos (métrica).

1. Comience a añadir una dimensión al proyecto en Analysis Workspace, tal como se describe en [Empezar a añadir componentes a un proyecto](#begin-adding-components-to-a-project).

1. Elija uno de los siguientes métodos para añadir dimensiones y determinar el tipo de datos que desea analizar:

   * Arrastre una dimensión a una visualización (como una tabla de forma libre) en Analysis Workspace.

     ![Adición de dimensiones a un proyecto](assets/add-dimensions.png)

   * Arrastre una o más dimensiones del carril izquierdo a la zona de colocación de segmentos para crear un segmento ad hoc, tal como se describe en [Añadir segmentos a un proyecto](#add-segments-to-a-project).

     ![colocar un segmento en la zona de colocación](assets/segment-dropzone.png)

1. (Opcional) Puede desglosar dimensiones y elementos de dimensión en Analysis Workspace con otros componentes.

   Para obtener más información, consulte [Desglose de dimensiones](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

Para obtener más información sobre el uso de dimensiones en Analysis Workspace, consulte [Previsualizar dimensiones](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Desglose de dimensiones](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md), y [Dimensiones de partición de tiempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Agregar métricas a un proyecto

[Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md) permite cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

Para agregar una métrica a un proyecto en Analysis Workspace:

1. Comience a añadir una métrica al proyecto en Analysis Workspace, tal como se describe en [Empezar a añadir componentes a un proyecto](#begin-adding-components-to-a-project).

1. Elija uno de los siguientes métodos para agregar una métrica en Analysis Workspace:

   * Arrastre una métrica a la zona de colocación de métricas en una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto.

     ![Adición de una métrica a un proyecto](assets/add-metrics.png)

   * Arrastrar una métrica cuando haya una dimensión presente para verla en comparación con cada elemento de dimensión.

   * Arrastrar una métrica sobre un encabezado de métrica existente para reemplazarla.

   * Arrastrar una métrica junto a un encabezado para ver ambas métricas en paralelo.

Para obtener más información sobre cómo utilizar las métricas en Analysis Workspace, consulte [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Añadir segmentos a un proyecto

[Segmentos](/help/components/segmentation/seg-overview.md) permiten identificar subconjuntos de visitantes en función de sus características o de interacciones específicas.

Puede utilizar segmentos en Analysis Workspace de cualquiera de las siguientes maneras:

### Adición de segmentos a un panel

Cuando agrega segmentos a un panel, los segmentos se aplican a todo el contenido del panel.

Para obtener información sobre cómo puede utilizar la zona de colocación de segmentos en un panel para filtrar el panel, consulte [Zona de colocación](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Información general de paneles](/help/analyze/analysis-workspace/c-panels/panels.md).

### Añadir segmentos a una columna en una tabla de forma libre

Cuando se añaden segmentos a una columna de una tabla de forma libre, los segmentos se aplican a todo el contenido de la columna de la tabla.

### Uso de segmentos al crear métricas calculadas

En el Creador de métricas calculadas, puede aplicar segmentos dentro de su definición de métrica.

Para obtener más información, consulte [Métricas segmentadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md).

## Adición de intervalos de fechas a un proyecto

[Intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) determine el lapso de tiempo de la creación de informes en Analysis Workspace y se pueda aplicar a uno o varios paneles dentro de un proyecto.

Cada panel incluye un intervalo de fechas de forma predeterminada. Existen varias formas de actualizar un intervalo de fechas para un panel. Una forma de actualizar el intervalo de fechas de un panel en Analysis Workspace es arrastrar un componente de intervalo de fechas desde el carril izquierdo:

1. Comience a añadir un intervalo de fechas al proyecto en Analysis Workspace, tal como se describe en [Empezar a añadir componentes a un proyecto](#begin-adding-components-to-a-project).

1. Arrastre un intervalo de fechas desde el carril izquierdo al intervalo de fechas actual en la parte superior derecha del panel.

   ![soltar un intervalo de fecha](assets/daterange-drop.png)

Para obtener más información sobre cómo utilizar calendarios e intervalos de fechas en Analysis Workspace, consulte [Resumen de calendario e intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).
