---
description: Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.
title: Habilitar Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: d4caf0ddc5cf5402bfef94a64db1c00e1c725658
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 74%

---

# Habilitar Activity Map{#enable-activity-map}

Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.

## Paso 1. Actualice el código de implementación {#section_5D1586289DF2489289B1B6C1C80C300D}

El módulo Activity Map forma parte de AppMeasurement.js y del SDK web (versión 2.15.0 o superior).
La biblioteca de AppMeasurement o el SDK web cargarán el módulo del Activity Map cuando se cree una instancia.

>[!NOTE]
>
>Los datos del Activity Map no se pueden recopilar a menos que actualice a **AppMeasurement** **versión 1.6** o superior o **SDK web** **versión 2.15.0** o superior.


1. Descargue la biblioteca JavaScript más reciente en función de si utiliza AppMeasurement o SDK web.

   - **AppMeasurement** codifique (AppMeasurement_Javascript-1.6.zip) accediendo a  **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Administrador de códigos]** y [implementarlo](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=es).

     Hemos incluido [código de implementación de muestra](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) para facilitar la visualización de los cambios que se han hecho en el código al incluir el módulo Activity Map.

   - **SDK web** código (alloy.js). Consulte [Instalación del SDK: Opción 2: Instalación de la versión independiente prediseñada](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=es#option-2%3A-installing-the-prebuilt-standalone-version) para obtener más información. Asegúrese de utilizar la versión 2.15 o posterior de.

     Consulte [Seguimiento de vínculos](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es) para obtener información sobre cómo implementar el seguimiento de vínculos y cómo habilitar Activity Mapping capturando el `region` del elemento de HTML donde se hizo clic.

     >[!NOTE]
     >
     >Al habilitar el seguimiento de vínculos con el SDK web, se envían eventos de vínculo cuando un cliente navega de una página a la siguiente. Se trata de un funcionamiento diferente al de AppMeasurement y puede dar lugar a que se envíen más visitas facturables a Adobe.


1. Validar la implementación:

   1. Cuando se hace clic en un elemento activo, los datos se guardan en una cookie llamada s_sq.
   1. Los datos de Activity Map se pueden ver en la cadena de consulta de la llamada de seguimiento. Por ejemplo:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Desglose este informe por **[!UICONTROL Vínculo de Activity Map por región]** para ver el vínculo o la región de esa página:  ![](assets/am_breakdown.png){width="400px"}

## Paso 2. Habilitar los informes de Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Primero hay que habilitar los informes de Activity Map en el nivel de grupo de informes.

1. Inicie sesión en Adobe Analytics y vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Selecionar un grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]**.
1. Activity Map recopila los datos sobre vínculos en informes de Activity Map. Para que se realice la activación, primero debe activar las variables haciendo clic en **[!UICONTROL Habilitar los informes de Activity Map]**.

   En este paso se añaden todas las dimensiones de Analytics que se necesitan para recopilar datos.

1. Cuando pase una hora más o menos, consulte el [informe Página de Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que muestra todas las páginas donde los usuarios han hecho clic en un vínculo.

## Paso 3. Añadir usuarios al grupo de acceso de Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Haga clic en **[!UICONTROL Agregar usuarios al grupo]**.

   Esto le llevará a la página de administración de grupos de Admin Console.

1. [Añada usuarios a este grupo](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=es) y haga clic en **[!UICONTROL Guardar grupo]**.

1. De este modo, sus usuarios administradores podrán descargar Activity Map desde **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Activity Map]**.

>[!NOTE]
>
>Si desea que los usuarios que no son administradores descarguen Activity Map, cree un nuevo grupo de usuarios que proporcione permisos para “Herramientas” e “Instalación heredada de ClickMap”. Este nivel de permiso combinado con el acceso a Activity Map proporciona permisos para descargar y utilizar la herramienta.
