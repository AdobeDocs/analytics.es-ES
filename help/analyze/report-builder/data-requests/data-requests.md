---
description: 'null'
title: 'Solicitudes de datos: Paso 1 del Asistente para solicitudes'
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Solicitudes de datos: Paso 1 del Asistente para solicitudes

En el formulario Asistente para solicitudes: Paso 1, se selecciona el grupo y el tipo de informes, así como los segmentos, y se configuran las fechas.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**:: La lista de los grupos de informes disponibles en función de las credenciales de inicio de sesión. See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Selector de rango:** permite seleccionar un ID de grupo de informes en una celda en Excel. Consulte [Seleccionar grupos de informes](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segmento**: los segmentos son subconjuntos de datos o datos filtrados mediante reglas que se han creado. Los segmentos se basan en visitas individuales, visitas y visitantes. Consulte la [Guía de segmentación de Analytics](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/seg-home.html) para obtener más información acerca de los segmentos.

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **Permitir anulación de la lista de publicación**: cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución. Las listas de publicación se configuran en **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. El grupo de informes de esta solicitud se reemplaza por el ID de grupo de informes asignado a cada destinatario incluido en la lista de publicación. Consulte [Permitir anulaciones de la lista de publicación](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Tipo de informe**: especifica el informe base que se desea ejecutar en la solicitud de datos. Por cada solicitud se ejecuta un informe, y éste puede tener de una a varias dimensiones y métricas. Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Intervalos de fechas**: define el lapso de tiempo abarcado por la solicitud. Existen distintos tipos de períodos de tiempo de solicitud como, por ejemplo, preestablecidos, fijos y móviles. El número máximo de períodos es 366. También puede seleccionar un intervalo de fechas especificado por una celda y guardar los intervalos de fechas como plantillas para su uso posterior.  Consulte [Configuración de fechas de informes](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Aplicar granularidad**: especifica el nivel de detalle basado en el tiempo que se incluye en el informe. Consulte [Granularidad](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

>[!MORELIKETHIS]
>
>* [Crear una solicitud de datos](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)

