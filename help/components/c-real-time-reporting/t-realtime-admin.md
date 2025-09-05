---
description: Pasos administrativos para configurar informes en tiempo real.
title: Configurar informes en tiempo real
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '271'
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
