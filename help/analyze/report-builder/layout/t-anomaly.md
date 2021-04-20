---
description: Los pasos describen cómo crear una solicitud de detección de anomalías en Report Builder.
title: Configuración de una solicitud de detección de anomalías
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 98%

---


# Configuración de una solicitud de detección de anomalías

Los pasos describen cómo crear una solicitud de detección de anomalías en Report Builder.

1. Seleccione un informe de tendencias, como por ejemplo el informe **[!UICONTROL Métricas del sitio]** > **[!UICONTROL Tráfico]**.
1. En el menú [!UICONTROL Aplicar granularidad], seleccione **[!UICONTROL Día]**.

   >[!NOTE]
   >
   >El menú [!UICONTROL Detección de anomalías] está disponible únicamente cuando selecciona la granularidad de día. Los 30 días previos de datos se utilizan como período de prueba de datos estadístico, independientemente del intervalo de fechas que haya seleccionado.

1. Tras configurar los intervalos de fechas, haga clic en **[!UICONTROL Siguiente]**.

   Resultado (1). En el Asistente para solicitudes: paso 2 de 2, añada una métrica como por ejemplo **[!UICONTROL Visitas]**.

   Resultado (1). En la métrica añadida, haga clic en el vínculo **[!UICONTROL Ninguno]**.

   ![Resultado](assets/anomaly_select.png)

1. Seleccione **[!UICONTROL Detección de anomalías]** > **[!UICONTROL `<selection>`]**.

   ![Información sobre los pasos](assets/anomaly_visit.png)

   Cuando selecciona una de estas opciones, el sistema crea copias de Detección de anomalías de la métrica original. Por ejemplo, en la métrica Visitas, la métrica de límite inferior de visitas se añade al grupo de [!UICONTROL Métrica].
1. Haga clic en **[!UICONTROL Finalizar]** y seleccione la celda para los resultados de Excel.

   Consulte [Detección de anomalías](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) para ver las definiciones.
