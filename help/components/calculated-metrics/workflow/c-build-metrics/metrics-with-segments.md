---
description: Aprenda a segmentar métricas individuales, lo que le permite realizar comparaciones de métricas dentro de la misma visualización.
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
TQID: https://experienceleague.adobe.com/t1HtjinGP02YSBQk1Z95t6wIQ0OhuFb14GKfpd8Y9Eg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 463
ht-degree: 1%

---

# Métricas segmentadas

En el [Creador de métricas calculadas](cm-build-metrics.md#definition-builder), puede aplicar segmentos dentro de su definición de métrica. La aplicación de segmentos resulta útil si desea utilizar métricas para un subconjunto de los datos en el análisis.

>[!NOTE]
>
>Las definiciones de segmentos se actualizan a través de [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md). Si realiza un cambio en un segmento, este se actualiza automáticamente en cualquier lugar donde se utilice, incluso si forma parte de una definición de métrica calculada.
>

Desea comparar las métricas de los alemanes que interactúan con su marca con las de otros fuera de Alemania. Por lo tanto, puede responder preguntas como:

1. ¿Cuántas personas alemanas o internacionales están visitando tus [páginas más populares](#popular-pages)?
1. ¿Cuántas personas alemanas versus internacionales en [total](#totals) han interactuado en línea con su marca este mes?
1. ¿Cuáles son los [porcentajes](#percentages) de alemanes y personas internacionales que han visitado tus páginas populares?

Consulte las secciones siguientes para ilustrar cómo las métricas segmentadas pueden ayudarle a responder a estas preguntas. Si procede, se hace referencia a documentación más detallada.

## Páginas populares

1. [Cree una métrica calculada](../cm-workflow.md) a partir de un proyecto de Workspace, denominado `Germany`.
1. Desde el [Creador de métricas calculadas](cm-build-metrics.md), [cree un segmento](/help/components/segmentation/segmentation-workflow/seg-build.md), con el título `Germany`, que esté usando el campo Países.

   >[!TIP]
   >
   >En el Creador de métricas calculadas, puede crear un segmento directamente mediante el panel Componentes.
   >   

   El segmento podría tener el aspecto siguiente:.

   ![Segmento Alemania](assets/segment-germany.png)

1. En el Creador de métricas calculadas, utilice el segmento para actualizar la métrica calculada.

   ![Métrica calculada Alemania](assets/germany-visits.png)

Repita los pasos anteriores para la versión internacional de la métrica calculada.

1. Cree una métrica calculada a partir del proyecto de Workspace, con el título `Non Germany visits`.
1. Desde el Creador de métricas calculadas, cree un segmento con el título `Not Germany` que esté usando el campo País de CRM a partir de los datos de CRM para determinar de dónde proviene una persona.

   El segmento debería tener el aspecto siguiente:.

   ![Segmento Alemania](assets/segment-not-germany.png)

1. En el Creador de métricas calculadas, utilice el segmento para actualizar la métrica calculada.

   ![Métrica calculada Alemania](assets/non-germany-visits.png)


1. Cree un proyecto en Analysis Workspace, donde verá las páginas visitadas por visitantes alemanes y no alemanes.

   ![Visualización de tabla de forma libre de Workspace que muestra personas alemanas frente a internacionales](assets/workspace-german-vs-international.png)


## Totales

1. Cree dos nuevas métricas calculadas basadas en el Total general. Abra cada uno de los segmentos creados anteriormente, cambie el nombre del segmento, establezca el **[!UICONTROL Tipo de métrica]** para **[!UICONTROL Personas]** en **[!UICONTROL Total general]** y use **[!UICONTROL Guardar como]** para guardar el segmento con el nuevo nombre. Por ejemplo:

   ![Métrica total para Alemania](assets/calculated-metric-germany-total.png)

1. Agregue una nueva visualización de tabla de forma libre a su proyecto de Workspace, que mostrará las páginas totales de este año.

   ![Visualización de tabla de forma libre de Workspace que muestra personas en alemán frente a personas en total internacionales](assets/workspace-german-vs-international-totals.png)


## Porcentajes

1. Cree dos nuevas métricas calculadas que calculen un porcentaje a partir de las métricas calculadas creadas anteriormente.

   ![Visualización de tabla de forma libre de Workspace que muestra el porcentaje de personas en alemán frente al total internacional](assets/calculated-metric-germany-total-percentage.png)


1. Actualice el proyecto de Workspace.

   ![Visualización de tabla de forma libre de Workspace que muestra personas en alemán frente a personas en total internacionales](assets/workspace-german-vs-international-totals-percentage.png)

