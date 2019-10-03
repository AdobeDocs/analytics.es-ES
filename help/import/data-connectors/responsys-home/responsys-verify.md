---
description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente mediante las siguientes comprobaciones.
seo-description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente mediante las siguientes comprobaciones.
seo-title: Verificación de la integración
solution: Analytics
title: Verificación de la integración
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# Verificación de la integración{#verifying-the-integration}

After deployment, you should validate that the integration is successfully transferring data through the following checks.

1. Vea el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades de integración]**.

      ![](assets/integration_activity_log.png)

   1. Busque entradas como Datos **[!UICONTROL de clasificación importados correctamente]**, Datos de **[!UICONTROL métricas importados correctamente]** y Datos de **[!UICONTROL métricas exportados correctamente]**. Estas entradas deben aparecer en el plazo de 1 día desde que se realizó correctamente la implementación.
1. View your reporting data within Adobe Analytics.

   1. Vaya a Conversión **** personalizada &gt; Conversión **[!UICONTROL personalizada 1-10]** &gt; Informes **[!UICONTROL de ID de]** mensaje.

      ![](assets/reporting.png)

   1. Busque informes de Responsys.  Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.
