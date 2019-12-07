---
description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente a través de las siguientes comprobaciones.
title: Verificación de la integración
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Verificación de la integración{#verifying-the-integration}

Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente a través de las siguientes comprobaciones.

1. Vea el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades de integración]**.

      ![](assets/integration_activity_log.png)

   1. Busque entradas como Datos **[!UICONTROL de clasificación importados correctamente]**, Datos de **[!UICONTROL métricas importados correctamente]** y Datos de **[!UICONTROL métricas exportados correctamente]**. Estas entradas deben aparecer en el plazo de 1 día desde que se realizó correctamente la implementación.
1. Vea los datos de los informes en Adobe Analytics.

   1. Vaya a Conversión **** personalizada &gt; Conversión **[!UICONTROL personalizada 1-10]** &gt; Informes **[!UICONTROL de ID de]** mensaje.

      ![](assets/reporting.png)

   1. Busque informes de Responsys. Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.
