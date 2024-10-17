---
description: Obtenga información sobre cómo crear una solicitud de detección de anomalías en Report Builder.
title: Configuración de una solicitud de detección de anomalías
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 72%

---

# Configuración de una solicitud de detección de anomalías

{{legacy-arb}}

Para crear una solicitud de detección de anomalías en Report Builder:

1. Seleccione un informe de tendencias, como por ejemplo el informe **[!UICONTROL Métricas del sitio]** > **[!UICONTROL Tráfico]**.
1. En el menú [!UICONTROL Aplicar granularidad], seleccione **[!UICONTROL Día]**.

   >[!NOTE]
   >
   >El menú [!UICONTROL Detección de anomalías] está disponible únicamente cuando selecciona la granularidad de día. Los 30 días previos de datos se utilizan como período de prueba de datos estadístico, independientemente del intervalo de fechas que haya seleccionado.

1. Tras configurar los intervalos de fechas, haga clic en **[!UICONTROL Siguiente]**.

   En el Asistente para solicitudes: paso 2 de 2, añada una métrica como por ejemplo **[!UICONTROL Visitas]**.

   En la métrica añadida, haga clic en el vínculo **[!UICONTROL Ninguno]**.

   ![Captura de pantalla que muestra la detección de anomalías y luego las opciones Insertar y luego insertar para los límites inferior y superior y esperado.](assets/anomaly_select.png)

1. Seleccione **[!UICONTROL Detección de anomalías]** > **[!UICONTROL `<selection>`]**.

   ![Captura de pantalla que muestra el paso 2 del Asistente para solicitudes - Informe de tráfico.](assets/anomaly_visit.png)

   Cuando selecciona una de estas opciones, el sistema crea copias de Detección de anomalías de la métrica original. Por ejemplo, en la métrica Visitas, la métrica de límite inferior de visitas se añade al grupo de [!UICONTROL Métrica].
1. Haga clic en **[!UICONTROL Finalizar]** y seleccione la celda para los resultados de Excel.

   Consulte [Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) para ver las definiciones.
