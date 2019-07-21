---
description: Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.
seo-description: Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.
seo-title: Habilitar Activity Map
solution: Analytics
title: Habilitar Activity Map
topic: Activity Map
uuid: 30433319-d 0 e 6-4977-951 a -4492 b 356 e 1 f 2
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Enable Activity Map{#enable-activity-map}

Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.

## Paso 1. Actualizar el código de AppMeasurement (Javascript) a v1.6 (o posterior) {#section_5D1586289DF2489289B1B6C1C80C300D}

El módulo Activity Map forma parte del archivo AppMeasurement.js (se encuentra al principio del archivo). La biblioteca AppMeasurement no cargará el módulo Activity Map cuando se creen instancias de este.

Los datos de Activity Map no se pueden recopilar si no actualiza a esta versión (o posterior) de AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Hemos incluido [código de implementación de muestra](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) para facilitar la visualización de los cambios que se han hecho en el código al incluir el módulo Activity Map.

1. Valide la implementación:

   1. Cuando se hace clic en un elemento activo, los datos se guardan en una cookie llamada s_sq.
   1. Los datos de Activity Map se pueden ver en la cadena de consulta de la llamada de seguimiento. Por ejemplo:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Paso 2: Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Primero hay que habilitar los informes de Activity Map en el nivel de grupo de informes.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. Activity Map recopila los datos sobre vínculos en informes de Activity Map. Para que se realice la activación, primero debe activar las variables haciendo clic en **[!UICONTROL Habilitar los informes de Activity Map]**.

   En este paso se añaden todas las dimensiones de Analytics que se necesitan para recopilar datos.

1. Cuando pase una hora más o menos, consulte el [informe Página de Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que muestra todas las páginas donde los usuarios han hecho clic en un vínculo.

## Paso 3. Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Haga clic en **[!UICONTROL Agregar usuarios al grupo]**.

   Esto le llevará a la página de administración de grupos de Admin Console.

1. [Añada usuarios a este grupo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) y haga clic en **[!UICONTROL Guardar grupo]**.

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> &gt; 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. A continuación, puede agregar usuarios no administradores a este grupo. Este nivel de permiso combinado con el Acceso a Mapa de actividades le proporcionará permisos completos para descargar y utilizar la herramienta. 
</note>
