---
description: Después de la implementación, debe validar que la integración transfiera correctamente los datos a través de las siguientes comprobaciones.
seo-description: Después de la implementación, debe validar que la integración transfiera correctamente los datos a través de las siguientes comprobaciones.
seo-title: Verificación de la integración
solution: Analytics
title: Verificación de la integración
uuid: 5 f 0 f 9 f 69-e 932-4472-8578-dd 3 af 1315 c 0 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Verifying the Integration{#verifying-the-integration}

Después de la implementación, debe validar que la integración transfiera correctamente los datos a través de las siguientes comprobaciones.

1. Vea el registro de actividad de integración.
   1. In the Adobe Marketing Cloud, navigate to **[!UICONTROL Support]** &gt; **[!UICONTROL Integration Activity Log]**.

      ![](assets/integration_activity_log.png)

   1. Look for entries like **[!UICONTROL Classification Data imported successfully]**, **[!UICONTROL Metrics Data imported successfully]**, and **[!UICONTROL Metric Data exported successfully]**. Estas entradas deben aparecer en un plazo de 1 día tras la correcta implementación.
1. Vea los datos de informes en Adobe Analytics.
   1. Navigate to **[!UICONTROL Custom Conversion]** &gt; **[!UICONTROL Custom Conversion 1-10]** &gt; **[!UICONTROL Message ID Reports]**.

      ![](assets/reporting.png)

   1. Busque los informes de Responsys. Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.
