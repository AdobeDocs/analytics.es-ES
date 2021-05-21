---
description: Desglose de dimensiones y elementos de dimensión en Analysis Workspace.
keywords: Analysis Workspace
title: Desglose de dimensiones
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Conceptos básicos de Workspace
role: Business Practitioner, Administrator
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '230'
ht-degree: 100%

---

# Desglose de dimensiones

Desglose de dimensiones y elementos de dimensión en Analysis Workspace.

Desglose los datos ilimitadamente para sus necesidades específicas; genere consultas con métricas, dimensiones, segmentos, líneas de tiempo y otros valores de desglose de análisis relevantes.

1. [Cree un proyecto](/help/analyze/analysis-workspace/home.md) con una tabla de datos.
1. En la tabla de datos, haga clic con el botón secundario en un elemento de línea y seleccione **[!UICONTROL Desglosar]** > *`<item>`*.

   ![Resultado](assets/fa_data_table_actions.png)

   Puede desglosar métricas por elementos de dimensión o segmentos de audiencia entre periodos de tiempo seleccionados. También puede continuar desglosando hasta un nivel más granular.

   >[!NOTE]
   >
   >El número de desgloses de la tabla está limitado a 200 desgloses. Este límite aumentará para la exportación de desgloses.

[Añadir Dimensión y métricas al proyecto en Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html) (11:39)

[Trabajo con Dimensiones en una tabla improvisada](https://docs.adobe.com/content/help/es-ES/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table.html) (15:35)

## Aplicar modelos de atribución a desgloses

Cualquier desglose dentro de una tabla también puede tener aplicado cualquier modelo de atribución. Este modelo de atribución puede ser el mismo o diferente de la columna principal. Por ejemplo, puede analizar Pedidos lineales en su dimensión de Canales de marketing pero aplicar Pedidos en forma de U a los códigos de seguimiento específicos dentro de un Canal. Para editar el modelo de atribución aplicado a un desglose, simplemente sitúe el ratón encima del modelo de desglose y haga clic en **[!UICONTROL Editar]**:

![Configuración del desglose](assets/breakdown_settings.png)
