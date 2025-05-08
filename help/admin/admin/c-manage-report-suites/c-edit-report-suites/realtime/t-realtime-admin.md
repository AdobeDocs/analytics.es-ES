---
description: Pasos administrativos para configurar informes en tiempo real.
title: Configuración de informes en tiempo real
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 76%

---

# Configuración de informes en tiempo real

Pasos administrativos para configurar informes en tiempo real.

Configurar informes en tiempo real en Adobe Analytics consiste en seleccionar el grupo de informes y configurar hasta 3 informes para este. De manera predeterminada todos los usuarios tienen acceso a los informes en tiempo real.

1. Seleccione el grupo de informes para el que quiere habilitar los informes en tiempo real.

   Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración > Grupos de informes]**.

1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Tiempo real]**.

1. Configure la recopilación de datos en tiempo real para hasta tres informes, con una métrica y tres dimensiones o clasificaciones por informe.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Para obtener información sobre las métricas y dimensiones compatibles en tiempo real, consulte [Métricas y dimensiones compatibles](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Si ha creado clasificaciones, estas aparecerán con sangría debajo de las dimensiones para las que se hayan definido:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Actualmente no se pueden duplicar dimensiones para un solo informe en tiempo real, aunque se seleccione una clasificación distinta para cada dimensión.

   >[!NOTE]
   >
   >Algunas dimensiones, como “Buscar palabra clave” o “Producto”, no persisten en tiempo real como lo hacen en el resto de Adobe Analytics. Al seleccionar una métrica no persistente se mostrará la siguiente advertencia:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   Después de esta configuración inicial del informe los datos pueden tardar hasta 20 minutos en ser transferidos. A partir de ese momento, los datos estarán disponibles inmediatamente.

1. Para ver el informe en tiempo real, vaya a:

   **[!UICONTROL Workspace]** > **[!UICONTROL Informes]** > **[!UICONTROL Participación]** > **[!UICONTROL Tiempo real]**.

