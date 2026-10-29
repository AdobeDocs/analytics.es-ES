---
description: Descubra cómo los administradores pueden agregar descripciones a los componentes mediante un grupo de informes o el diccionario de datos.
title: Adición de descripciones de componentes
feature: Components
role: Admin
exl-id: db36ee4a-66e2-45d1-8b7a-49570b5fce93
TQID: https://experienceleague.adobe.com/8z9vnSfrxEb1nkOlTTlHrp3BdElFJmTjbsSLBGbE7Gs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b3d9fb81837398b349496ec261dc1d0ba3df3645
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 20%
---
# Adición de descripciones de componentes

Las descripciones ayudan a los usuarios a utilizar mejor los distintos componentes cuando crean proyectos en Analysis Workspace o al ver informes.

Los administradores de Analytics pueden agregar descripciones para los componentes (dimensiones, métricas, segmentos e intervalos de fechas) dentro de un grupo de informes o utilizando el diccionario de datos directamente en Analysis Workspace.

## Grupo de informes

Puede agregar descripciones a los componentes de un grupo de informes.

1. Seleccione **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Grupos de informes]**.
1. Seleccione el grupo de informes en el Administrador del grupo de informes para el que desea proporcionar descripciones de componentes.
1. Seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de conversión]**.
1. Seleccione ![Agregar](/help/assets/icons/Add.svg) para mostrar los detalles de una variable de conversión.
1. Seleccione la casilla de verificación de **[!UICONTROL Descripción]** y agregue una descripción.
1. Repita los pasos 4 y 5 para cualquier otra variable a la que desee agregar una descripción.
1. Seleccione **[!UICONTROL Guardar]**.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Agregar descripciones de componentes](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/intro-to-analytics/customizing-the-ui/adding-dimension-and-metric-descriptions){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Diccionario de datos {#add-descriptions}

El diccionario de datos de Analysis Workspace ayuda a los usuarios y administradores a seguir los componentes de su entorno de Analytics y a comprenderlos mejor. El diccionario de datos permite a los administradores de Analytics añadir descripciones de componentes directamente en Analysis Workspace.

Para obtener información sobre cómo editar una descripción de componente en el diccionario de datos, consulte [Editar entradas de componente en el diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

Para obtener información general sobre el diccionario de datos, consulte [Información general del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Configuración del componente de informe](/help/components/vrs/vrs-components.md)
>[Entradas del componente del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Generar descripciones automáticamente

{{release-limited-testing-section}}

En lugar de escribir cada descripción manualmente, Adobe Analytics puede utilizar IA generativa para escribir descripciones. Puede generar una descripción para un solo componente o generar descripciones para muchos componentes al mismo tiempo.

Descripciones generadas:

* No tienen más de 3 frases.
* Finalice con el texto **[!UICONTROL Generado por Adobe mediante IA]**, de modo que los usuarios sepan que se generó la descripción.
* Se pueden editar una vez generados.

### Requisitos previos

Antes de poder generar descripciones, su organización debe aceptar determinados términos legales de IA generativa. Si su organización no ha aceptado estos términos, la opción para generar descripciones aparece atenuada. Seleccione el icono de información ![Información](/help/assets/icons/InfoOutline.svg) junto a la opción para obtener información sobre cómo habilitar la función o póngase en contacto con el administrador de su organización o con el equipo de cuenta de Adobe.

### Cómo se generan las descripciones

Las descripciones generadas se basan en la definición del componente y en un contexto adicional sobre cómo se utiliza el componente en el grupo de informes, como:

* Los elementos principales de una dimensión
* Componentes que se utilizan con frecuencia con el componente

Cuando una métrica calculada o un segmento hace referencia a otro segmento, la descripción generada explica la definición del segmento al que se hace referencia.

### Generar descripciones desde varias ubicaciones

Puede generar descripciones en las siguientes áreas de Adobe Analytics. Algunas ubicaciones permiten generar descripciones para varios componentes, mientras que otras no.

Seleccione una ubicación para aprender a generar descripciones allí.

| Ubicación | Componentes compatibles | Componente único | Múltiples componentes |
| --- | --- | --- | --- |
| [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensiones</li><li>Métricas</li><li>Métricas calculadas</li><li>Segmentos</li><li>Intervalos de fechas</li></ul> | Sí | Sí |
| [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) | Segmentos | Sí | No |
| [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md#action-bar) | Segmentos | No | Sí |
| [Generador de métricas calculadas](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) | Métricas calculadas | Sí | No |
| [Administrador de métricas calculadas](/help/components/calculated-metrics/workflow/cm-manager.md#action-bar) | Métricas calculadas | No | Sí |
| [Generador de intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/create.md#date-range-builder) | Intervalos de fechas | Sí | No |
| [Administrador de intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/manage.md#action-bar) | Intervalos de fechas | No | Sí |

{style="table-layout:auto"}