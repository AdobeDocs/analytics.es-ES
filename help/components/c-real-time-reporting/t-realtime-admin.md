---
description: Pasos administrativos para configurar informes en tiempo real.
title: Configurar informes en tiempo real
topic: Admin tools
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Configurar informes en tiempo real

Pasos administrativos para configurar informes en tiempo real.

Configurar informes en tiempo real en [!UICONTROL Reports & Analytics] consiste en seleccionar el grupo de informes y configurar hasta 3 informes para este.

1. Seleccione el grupo de informes para el que quiere habilitar los informes en tiempo real.

   Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]** > **[!UICONTROL Real-Time]** y seleccione el grupo de informes en la lista desplegable de la parte superior:

   ![](assets/report_suite_selector.png)

   Si trata de ver informes en tiempo real de un grupo de informes que no se haya configurado para este tipo de informes, aparecerá un mensaje que le permitirá configurarlo.

   ![](assets/rep_suite_not_set_up.png)

1. Haga clic en **[!UICONTROL Configure]** (icono de engranaje) para ejecutar el [!UICONTROL Report Suite Manager].

   (También disponible en **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**).

1. Encienda la **[!UICONTROL Enable Real-Time]** configuración.
1. Configure la recopilación de datos en tiempo real para hasta tres informes, con una métrica y tres dimensiones o clasificaciones por informe.

   ![](assets/real_time_admin.png)

   Para obtener información sobre las métricas y dimensiones compatibles en tiempo real, consulte [Métricas y dimensiones compatibles](/help/components/c-real-time-reporting/realtime-metrics.md).

   Si ha creado clasificaciones, estas aparecerán con sangría debajo de las dimensiones para las que se hayan definido:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Actualmente no se pueden duplicar dimensiones para un solo informe en tiempo real, aunque se seleccione una clasificación distinta para cada dimensión.

   Para obtener más información sobre las clasificaciones, consulte [Acerca de las clasificaciones](/help/components/c-classifications2/c-classifications.md).

   >[!NOTE]
   >
   >Algunas dimensiones, como “Buscar palabra clave” o “Producto”, no persisten en tiempo real como lo hacen en el resto de Adobe Analytics. Al seleccionar una métrica no persistente se mostrará la siguiente advertencia:

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   Después de esta configuración inicial del informe los datos pueden tardar hasta 20 minutos en ser transferidos. A partir de ese momento los datos estarán disponibles inmediatamente. Para obtener más información sobre la visualización de informes en tiempo real, consulte [Ejecución de un informe en tiempo real](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/t-running-report-types.html).

1. De manera predeterminada todos los usuarios tienen acceso a los informes en tiempo real.
