---
description: Pasos administrativos para configurar informes en tiempo real.
title: Configurar informes en tiempo real
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: 'https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: e3f5b014-59dd-41c0-90f5-c405dcfaed07
    internal-label: Real time reporting
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 74%
---
# Configurar informes en tiempo real

La siguiente información contiene pasos administrativos para configurar informes en tiempo real.

Esto consiste en seleccionar el grupo de informes y configurar hasta 3 informes para él.

1. Seleccione el grupo de informes para el que quiere habilitar los informes en tiempo real.

   1. En Analysis Workspace, seleccione la ficha [!UICONTROL **Workspace**] y, a continuación, seleccione [!UICONTROL **Informes**] > [!UICONTROL **Participación**] > **[!UICONTROL Tiempo real]**.

   1. Seleccione el grupo de informes en la lista desplegable de la parte superior:

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      Si trata de ver informes en tiempo real de un grupo de informes que no se haya configurado para este tipo de informes, aparecerá un mensaje que le permitirá configurarlo.

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. Seleccione **[!UICONTROL Configurar]** para ejecutar el [!UICONTROL Administrador del grupo de informes].

   (También disponible en **[!UICONTROL Analytics]** > **[!UICONTROL Administración > Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Tiempo real]**).

1. Habilite la configuración **[!UICONTROL Habilitar Tiempo real]**.
1. Configure la recopilación de datos en tiempo real para hasta tres informes, con una métrica y tres dimensiones o clasificaciones por informe.

   ![](assets/real_time_admin.png)

   Para obtener información sobre las métricas y dimensiones compatibles en tiempo real, consulte [Métricas y dimensiones compatibles](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Si ha creado clasificaciones, estas aparecerán con sangría debajo de las dimensiones para las que se hayan definido:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Actualmente no se pueden duplicar dimensiones para un solo informe en tiempo real, aunque se seleccione una clasificación distinta para cada dimensión.

   >[!NOTE]
   >
   >Algunas dimensiones, como “Buscar palabra clave” o “Producto”, no persisten en tiempo real como lo hacen en el resto de Adobe Analytics. Al seleccionar una métrica no persistente se mostrará la siguiente advertencia:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Seleccione **[!UICONTROL Guardar]** o **[!UICONTROL Guardar y ver informe]**.

   Después de esta configuración inicial del informe los datos pueden tardar hasta 20 minutos en ser transferidos. A partir de ese momento, los datos estarán disponibles inmediatamente.

1. De manera predeterminada todos los usuarios tienen acceso a los informes en tiempo real.
