---
description: Explica los pasos que debe completar el administrador de Analytics para habilitar la recopilación de vínculos de [!DNL Activity Map] y la descarga del usuario.
seo-description: Explica los pasos que debe completar el administrador de Analytics para habilitar la recopilación de vínculos de [!DNL Activity Map] y la descarga del usuario.
seo-title: Habilitar [!DNL Activity Map]
solution: Analytics
title: Habilitar [!DNL Activity Map]
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Activar [!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## Paso 1. Actualizar el código de AppMeasurement (Javascript) a v1.6 (o posterior) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map]Los datos de no se pueden recopilar si no actualiza a esta versión (o posterior) de AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Hemos incluido [código de implementación de muestra](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) para facilitar la visualización de los cambios que se han hecho en el código al incluir el módulo [!DNL Activity Map]

1. Valide la implementación:

   1. Cuando se hace clic en un elemento activo, los datos se guardan en una cookie llamada s_sq.
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. Por ejemplo:

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Paso 2: Habilitar [!DNL Activity Map] informes {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] recopila los datos del vínculo en [!DNL Activity Map] los informes. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   En este paso se añaden todas las dimensiones de Analytics que se necesitan para recopilar datos.

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## Paso 3. Add users to [!DNL Activity Map] access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Haga clic en **[!UICONTROL Agregar usuarios al grupo]**.

   Esto le llevará a la página de administración de grupos de Admin Console.

1. [Añada usuarios a este grupo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) y haga clic en **[!UICONTROL Guardar grupo]**.

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  Si desea que los usuarios que no son administradores descarguen [!DNL Activity Map], debe crear un nuevo grupo de usuarios que proporcione permisos para <span class="uicontrol"> Herramientas </span> &gt; <span class="uicontrol"> Instalación heredada de ClickMap </span>. A continuación, puede agregar usuarios que no sean administradores a este grupo. Este nivel de permiso combinado con el [!DNL Activity Map] Access proporcionará permisos completos para descargar y utilizar la herramienta. 
</note>
