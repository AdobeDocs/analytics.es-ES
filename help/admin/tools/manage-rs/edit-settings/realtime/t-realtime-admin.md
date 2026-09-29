---
description: Pasos administrativos para configurar informes en tiempo real.
title: Configuración de informes en tiempo real
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: 'https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: e3f5b014-59dd-41c0-90f5-c405dcfaed07
    internal-label: Real time reporting
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 76%
---
# Configuración de informes en tiempo real

Pasos administrativos para configurar informes en tiempo real.

Configurar informes en tiempo real en Adobe Analytics consiste en seleccionar el grupo de informes y configurar hasta 3 informes para este. De manera predeterminada todos los usuarios tienen acceso a los informes en tiempo real.

1. Seleccione el grupo de informes para el que quiere habilitar los informes en tiempo real.

   Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración > Grupos de informes]**.

1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Tiempo real]**.

1. Configure la recopilación de datos en tiempo real para hasta tres informes, con una métrica y tres dimensiones o clasificaciones por informe.

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   Para obtener información sobre las métricas y dimensiones compatibles en tiempo real, consulte [Métricas y dimensiones compatibles](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Si ha creado clasificaciones, estas aparecerán con sangría debajo de las dimensiones para las que se hayan definido:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Actualmente no se pueden duplicar dimensiones para un solo informe en tiempo real, aunque se seleccione una clasificación distinta para cada dimensión.

   >[!NOTE]
   >
   >Algunas dimensiones, como “Buscar palabra clave” o “Producto”, no persisten en tiempo real como lo hacen en el resto de Adobe Analytics. Al seleccionar una métrica no persistente se mostrará la siguiente advertencia:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   Después de esta configuración inicial del informe los datos pueden tardar hasta 20 minutos en ser transferidos. A partir de ese momento, los datos estarán disponibles inmediatamente.

1. Para ver el informe en tiempo real, vaya a:

   **[!UICONTROL Workspace]** > **[!UICONTROL Informes]** > **[!UICONTROL Participación]** > **[!UICONTROL Tiempo real]**.

