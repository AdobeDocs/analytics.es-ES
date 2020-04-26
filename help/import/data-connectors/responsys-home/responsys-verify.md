---
description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente a través de los siguientes métodos.
title: Verificación de la integración
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Verificación de la integración {#verifying-the-integration}

Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente a través de los siguientes métodos.

1. Vea el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** > **[!UICONTROL Registro de actividades de integración]**.

      ![](assets/integration_activity_log.png)

   1. Busque entradas como **[!UICONTROL Datos de clasificación importados correctamente]**, **[!UICONTROL Datos de métricas importados correctamente]** y **[!UICONTROL Datos de métricas exportados correctamente]**. Estas entradas deberían aparecer en el plazo de 1 día desde que se realizó la implementación.
1. Vea los datos de los informes en Adobe Analytics.

   1. Vaya a **[!UICONTROL Conversión personalizada]** > **[!UICONTROL Conversión personalizada 1-10]** > **[!UICONTROL Informes de ID de mensaje]**.

      ![](assets/reporting.png)

   1. Busque los informes de Responsys. Estos datos deberían aparecer entre 24 y 48 horas después de la implementación.
