---
description: 'null'
seo-description: 'null'
seo-title: Solicitudes de datos - Paso 1 del Asistente para solicitudes
title: Solicitudes de datos - Paso 1 del Asistente para solicitudes
uuid: 717542 c 3-e 4 aa -4 e 00-b 0 ca-cadecd 219 d 13
translation-type: tm+mt
source-git-commit: 1e7dc9c769a9980e7b60bd395e7c68d5e446dae3

---


# Solicitudes de datos - Paso 1 del Asistente para solicitudes

En el formulario Asistente para solicitudes: Paso 1, se selecciona el grupo y el tipo de informes, así como los segmentos, y se configuran las fechas.

![](assets/rw1_overview.png)

1. **[!UICONTROL Grupo de informes:]** lista de los grupos de informes que están a su disposición en función de sus credenciales de inicio de sesión. See [Select Report Suites](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **Selector de rango:** permite seleccionar un ID de grupo de informes en una celda en Excel. Consulte [Seleccionar grupos de informes](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).

1. **Segmento**: los segmentos son subconjuntos de datos o datos filtrados mediante reglas que se han creado. Los segmentos se basan en visitas individuales, visitas y visitantes. Consulte la [Guía de segmentación de Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) para obtener más información acerca de los segmentos.

   Por ejemplo, puede ejecutar un [!UICONTROL Informe de páginas] y, a continuación, aplicar el segmento Primeras visitas.

1. **Permitir anulación de la lista de publicación**: cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución. Publishing lists are set up in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin tools]**. El grupo de informes de esta solicitud se reemplaza por el ID de grupo de informes asignado a cada destinatario incluido en la lista de publicación. Consulte [Permitir anulaciones de la lista de publicación](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C).

1. **Tipo de informe**: especifica el informe base que se desea ejecutar en la solicitud de datos. Por cada solicitud se ejecuta un informe, y éste puede tener de una a varias dimensiones y métricas. La métrica y las dimensiones de un tipo de informe se muestran en la interfaz del [!UICONTROL Asistente para solicitudes: Paso 2]. Consulte [Seleccione Tipos de informes](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).

1. **Intervalos de fechas**: define el lapso de tiempo abarcado por la solicitud. Existen distintos tipos de períodos de tiempo de solicitud como, por ejemplo, preestablecidos, fijos y móviles. El número máximo de períodos es 366. También puede seleccionar un intervalo de fechas especificado por una celda y guardar los intervalos de fechas como plantillas para su uso posterior.  See [Configuring Report Dates](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Aplicar granularidad**: especifica el nivel de detalle basado en el tiempo que se incluye en el informe. Consulte [Granularidad](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).

>[!MORE_LIKE_THIS]
>
>* [Crear una solicitud de datos](/help/analyze/report-builder/data-requests/t-create-a-data-request.md)