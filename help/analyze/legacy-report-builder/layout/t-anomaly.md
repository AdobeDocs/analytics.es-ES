---
description: Obtenga información sobre cómo crear una solicitud de detección de anomalías en Report Builder.
title: Configuración de una solicitud de detección de anomalías
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

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

   Al seleccionar una de estas opciones, el sistema crea copias de Detección de anomalías de la métrica original. Por ejemplo, para la métrica Visitas, se agrega una métrica Visitas de límite inferior al grupo [!UICONTROL Métrica].
1. Haga clic en **[!UICONTROL Finalizar]** y seleccione la celda para los resultados de Excel.

   Consulte [Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) para ver las definiciones.
