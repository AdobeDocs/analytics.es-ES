---
description: Puede utilizar las dimensiones Audiencia de Adobe Audience Manager en todo Analytics. Los segmentos integrados son nuevas dimensiones de Analytics llamadas ID de audiencias y Nombre de audiencias, y pueden utilizarse como cualquier otra dimensión que Analytics recopile. En Fuentes de datos, los ID de audiencia se almacenan en la columna “mc_audiences”. Estas dimensiones no están disponibles en este momento en Data Workbench o Livestream. Estos son algunos ejemplos de cómo puede aprovechar las dimensiones Audiencias
solution: Experience Cloud
title: Utilización de los datos de audiencias en Analytics
feature: Audience Analytics
exl-id: c1c0a9de-4051-4073-82c1-5615b0f01fa9
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 89%

---

# Utilización de los datos de audiencias en Analytics

Puede utilizar las dimensiones Audiencia de Adobe Audience Manager en todo Analytics. Los segmentos integrados son nuevas dimensiones de Analytics llamadas ID de audiencias y Nombre de audiencias, y pueden utilizarse como cualquier otra dimensión que Analytics recopile. En Fuentes de datos, los ID de audiencia se almacenan en la columna “mc_audiences”. Estas dimensiones no están disponibles en este momento en Data Workbench o Livestream. Estos son algunos ejemplos de cómo puede aprovechar las dimensiones Audiencias:

## Analysis Workspace {#workspace}

En Analysis Workspace, los segmentos de Adobe Audience Manager aparecen como dos dimensiones.

1. Vaya a **[!UICONTROL Workspace]**.
1. En la lista de **[!UICONTROL Dimensiones]**, seleccione **[!UICONTROL ID de audiencia]** o **[!UICONTROL Nombre de audiencia]**. Nombre es una clasificación descriptiva del ID.

   ![](assets/aw-mcaudiences.png)

## Comparación de segmentos {#compare}

[Comparación de segmentos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=es) detecta las diferencias estadísticamente más significativas entre dos segmentos. Los datos de audiencias pueden usarse de dos maneras en Comparación de segmentos: 1) como los 2 segmentos que se comparan; y 2) como elementos de la tabla “Elementos de dimensiones principales”.

1. Vaya a **[!UICONTROL Workspace]** y seleccione el panel **[!UICONTROL Comparación de segmentos]** en el carril izquierdo.

1. Busque [!UICONTROL Nombre de audiencias] en el menú **[!UICONTROL Componente]**.

1. Abra [!UICONTROL Nombre de audiencias] para que aparezcan los elementos de dimensiones relacionados.
1. Arrastre las audiencias que desee comparar al generador de Comparación de segmentos.
1. (Opcional): puede incluir otros elementos de dimensiones o segmentos, hasta dos.
1. Haga clic en **[!UICONTROL Crear]**.

   Las dimensiones ID de audiencias y Nombre de audiencias aparecen automáticamente en la tabla “Elementos de dimensiones principales”, al igual que los datos de perfil adicionales para los dos segmentos que se comparan.

   ![](assets/aud-segcompare.png)

## Viaje del cliente (Flujo) en Analysis Workspace {#flow}

Los datos de segmentos de Adobe Audience Manager se pasan a Analytics para cada visita y representan el estado de pertenencia de un visitante a las distintas audiencias en un momento dado. Esto significa que un visitante podría encajar en un segmento (p. ej., “Conocimiento”) y más tarde tener la cualificación para un segmento superior (p. ej., “Consideración”). Puede utilizar [Flujo](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=es) en Analysis Workspace para visualizar el viaje que realiza un visitante entre audiencias.

1. Vaya a **[!UICONTROL Workspace]** y seleccione el panel **[!UICONTROL Flujo]** en el carril izquierdo.

1. Arrastre la dimensión [!UICONTROL Nombre de audiencia] al generador de Flujo.
1. Haga clic en **[!UICONTROL Crear]**.
1. (Opcional): Arrastre cualquier otra dimensión a la visualización Flujo para crear un [Flujo entre dimensiones](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html?lang=es).

![](assets/flow-aamaudiences.png)

Las audiencias también pueden utilizarse en las [visualizaciones de visitas en el orden previsto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=es).

## Visualización de Venn en Analysis Workspace {#venn}

Las [visualizaciones de Venn](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=es) muestran el solapamiento entre un máximo de 3 segmentos.

1. Vaya a **[!UICONTROL Workspace]** y seleccione la visualización **[!UICONTROL Venn]** en el carril izquierdo.

1. Busque [!UICONTROL Nombre de audiencias] en el menú de componentes.
1. Abra [!UICONTROL Nombre de audiencia] para que aparezcan los elementos de dimensiones relacionados.
1. Arrastre las audiencias que desee comparar al generador de Venn.
1. (Opcional): puede incluir otros elementos de dimensiones o segmentos, hasta tres.
1. Haga clic en **[!UICONTROL Crear]**.

![](assets/venn-viz.png)

## Generador de segmentos {#builder}

Puede incorporar las dimensiones Audiencias al [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) de Analytics junto con la información de comportamiento que Analytics recopila.

1. Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]**.
1. Haga clic en **[!UICONTROL Agregar]** para crear un segmento nuevo.
1. Después de ponerle nombre al segmento, arrastre la dimensión [!UICONTROL Nombre de audiencia] al panel Definiciones.
1. (Opcional): agregue otros criterios al segmento.
1. Guarde el segmento.

   ![](assets/aud-segbuilder.png)

