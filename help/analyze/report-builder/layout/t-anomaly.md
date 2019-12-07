---
description: Los pasos describen cómo crear una solicitud de detección de anomalías en el creador de informes.
title: Configuración de una solicitud de detección de anomalías
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configuración de una solicitud de detección de anomalías

Los pasos describen cómo crear una solicitud de detección de anomalías en el Creador de informes.

1. Seleccione un informe de tendencias, como por ejemplo el informe **Métricas del sitio** &gt; **[!UICONTROL Tráfico]**.
1. En el menú [!UICONTROL Aplicar granularidad]**, seleccione[!UICONTROL Día]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. Los 30 días previos de datos se utilizan como período de prueba de datos estadístico, independientemente del intervalo de fechas que haya seleccionado.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Resultado (1). On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Resultado (1). For the added metric, click the **[!UICONTROL None]** link.

   ![Resultado de pasos](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![Información sobre los pasos](assets/anomaly_visit.png)

   Cuando selecciona una de estas opciones, el sistema crea copias de Detección de anomalías de la métrica original. Por ejemplo, en la métrica Visitas, la métrica de límite inferior de visitas se añade al grupo de [!UICONTROL Métrica].
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.
