---
description: Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.
title: Habilitar Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 23%

---


# Activar y activar Activity Map

Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.

## Paso 1. Activar Activity Map {#update_code}

El módulo Activity Map forma parte de AppMeasurement.js, Adobe Experience Platform tags y el SDK web (alloy.js). Los datos del Activity Map no se pueden recopilar a menos que actualice a **SDK web versión 2.15.0** o superior, o **Extensión de Adobe Analytics tags v1.90** o superior, o **AppMeasurement versión 1.6** o superior.

+++SDK web (extensión de Adobe Experience Platform tags)

1. En Adobe Experience Platform tags, vaya a la propiedad para la que va a implementar Analytics. En [!UICONTROL Extensiones] -> [!UICONTROL SDK web de Adobe Experience Platform], seleccione **[!UICONTROL Habilitar la recopilación de datos de clics]** como se destaca a continuación.
1. Cree la biblioteca con los cambios.
1. Publique la biblioteca en producción.

![](assets/web_sdk.png)

**Validación**

Interactuar llamadas mediante la pestaña de red de Developer Console:

1. Cargue el script de Launch de desarrollo en el sitio.
1. Al hacer clic en Elementos, busque &#39;/ee&#39; en la pestaña Red

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Descargue e instale [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Ir a [!UICONTROL Registros] > [!UICONTROL Edge] > [!UICONTROL Conectar con Edge].

   ![](assets/validation2.jpg)

**Preguntas frecuentes**

* **La llamada de interacción no se activa en la pestaña Red (Network).**
La recopilación de datos por clic en una llamada a recopilar. Necesitamos filtrar con &quot;/ee&quot; o &quot;recopilar?&quot;

* **No se muestra la carga útil para la llamada a cobro revertido.**
La llamada a cobro revertido está diseñada de tal manera que el seguimiento no debería afectar la navegación a otros sitios, por lo que la función de descarga de documentos es aplicable a las llamadas a cobro revertido. Esto no afectará a la recopilación de datos, pero si necesita realizar la validación en la página, añada target = &quot;_blank&quot; al elemento correspondiente. A continuación, el vínculo se abre en una nueva pestaña.

* **¿Cómo ignoro la colección de PII?**
Añada las condiciones respectivas en&lt;&lt; on before link click send callback>> y devuelva el valor &quot;False&quot; para ignorar esos valores. [Más información](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es)

  Código de muestra:

  ![](assets/sample-code.png)

+++

+++Implementación manual del SDK web

Consulte [Seguimiento de vínculos](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es) para obtener información sobre cómo implementar el seguimiento de vínculos y cómo habilitar Activity Map capturando el `region` del elemento de HTML donde se hizo clic.

>[!NOTE]
>
>Actualmente, habilitar el seguimiento de vínculos con el SDK web envía eventos de vínculo cuando un cliente navega de una página a otra. Esto es diferente al funcionamiento de los AppMeasurementes y puede resultar en visitas facturables adicionales enviadas a los Adobes.

+++

+++Extensión de Analytics (Adobe Experience Platform tags)

En Adobe Experience Platform tags, vaya a la propiedad para la que va a implementar Analytics. En el [!UICONTROL Instalar extensión] diálogo, seleccione **[!UICONTROL Usar Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Descargue la biblioteca JavaScript más reciente para AppMeasurement.
Ir a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Administrador de códigos]**.
1. Impleméntelo mediante lo siguiente [estas instrucciones](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=es).

+++

## Paso 2. Habilitar los informes de Activity Map {#enable}

Debe habilitar los informes de Activity Map en el nivel de grupo de informes.

1. Inicie sesión en Adobe Analytics y vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Selecionar un grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]**.

1. Activity Map recopila los datos sobre vínculos en informes de Activity Map. Para que se realice la activación, primero debe activar las variables haciendo clic en **[!UICONTROL Habilitar los informes de Activity Map]**.

   En este paso se añaden todas las dimensiones de Analytics que se necesitan para recopilar datos.

   ![](assets/enable.png)

1. Cuando pase una hora más o menos, consulte el [informe Página de Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que muestra todas las páginas donde los usuarios han hecho clic en un vínculo.

## Paso 3. Añadir usuarios a [!UICONTROL Acceso de Activity Map] perfil de producto {#add_users}

1. Haga clic en **[!UICONTROL Agregar usuarios al grupo]**.

   Esto lo llevará a la página de perfil de producto en la [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Si no ha creado un [!UICONTROL Acceso de Activity Map] perfil de producto, hágalo ahora. Los elementos de permiso necesarios para este perfil son [!UICONTROL Herramientas de Analytics] > [!UICONTROL Activity Map] y [!UICONTROL Herramientas de Analytics] > [!UICONTROL Publicación de segmentos].

1. Añada usuarios a ese perfil de producto. Esto permite a los usuarios descargar Activity Map de  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL ActivityMap]** .

