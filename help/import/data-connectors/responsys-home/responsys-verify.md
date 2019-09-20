---
description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente mediante las siguientes comprobaciones.
seo-description: Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente mediante las siguientes comprobaciones.
seo-title: Verificación de la integración
solution: Analytics
title: Verificación de la integración
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Verificación de la integración{#verifying-the-integration}

Después de la implementación, debe validar que la integración esté transfiriendo datos correctamente mediante las siguientes comprobaciones.

1. Vea el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades de integración]**.

      ![](assets/integration_activity_log.png)

   1. Busque entradas como Datos **[!UICONTROL de clasificación importados correctamente]**, Datos de **[!UICONTROL métricas importados correctamente]** y Datos de **[!UICONTROL métricas exportados correctamente]**. Estas entradas deben aparecer en el plazo de 1 día desde que se realizó correctamente la implementación.
1. Vea los datos de los informes en Adobe Analytics.
   1. Vaya a Conversión **** personalizada &gt; Conversión **[!UICONTROL personalizada 1-10]** &gt; Informes **[!UICONTROL de ID de]** mensaje.

      ![](assets/reporting.png)

   1. Busque informes de Responsys.  Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.
