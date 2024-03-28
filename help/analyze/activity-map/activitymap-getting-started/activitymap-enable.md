---
description: Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.
title: Habilitar Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---


# Activación y habilitación de Activity Map

Explica los pasos que el administrador de Analytics debe llevar a cabo para habilitar la recopilación de vínculos de Activity Map y la descarga de los usuarios.

## Paso 1. Activar Activity Map {#update_code}

El módulo Activity Map forma parte de las etiquetas de AppMeasurement.js, Adobe Experience Platform y el SDK web (alloy.js). Los datos de Activity Map no se pueden recopilar a menos que actualice a **Web SDK versión 2.15.0** o superior, o a **Adobe Analytics tags extensión v1.90** o superior, o a **AppMeasurement versión 1.6** o superior.

+++Web SDK (extensión de etiquetas de Adobe Experience Platform)

1. En las etiquetas de Adobe Experience Platform, vaya a la propiedad para la que está implementando Analytics. En [!UICONTROL Extensiones] -> [!UICONTROL SDK web de Adobe Experience Platform], seleccione **[!UICONTROL Habilitar colección de datos de clics]** como se resalta a continuación.
1. Genere la Biblioteca con los cambios.
1. Publique la biblioteca en producción.

![](assets/web_sdk.png)

**Validación**

Llamadas interactivas mediante la pestaña Red de Developer Console:

1. Cargue el script de lanzamiento de desarrollo en el sitio.
1. Al hacer clic en Elementos, busque &quot;/ee&quot; en la pestaña Red.

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Descargue e instale [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Vaya a [!UICONTROL Registros] > [!UICONTROL Edge] > [!UICONTROL Conectarse a Edge].

   ![](assets/validation2.jpg)

**Preguntas frecuentes**

* **La llamada interactiva no se activa en la pestaña Red.**
Para recoger los datos de los clics en una llamada a cobro revertido, debemos filtrar con &quot;/ee&quot; o &quot;collect?&quot;

* **No hay visualización de carga útil para la llamada a cobro revertido.**
La llamada a cobro revertido está diseñada de tal manera que el seguimiento no debe afectar a la navegación a otros sitios, por lo que la función de descarga de documentos es aplicable a las llamadas a cobro revertido. Esto no afectará a la recopilación de datos, pero si necesita validar en la página, añada target = &quot;_blank&quot; al elemento correspondiente. A continuación, el enlace se abre en una nueva pestaña.

* **¿Cómo ignoro la colección de PII?**
Añada las condiciones respectivas en &lt;&lt; on before link click send callback>> y devuelva false para ignorar esos valores. [Más información](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es)

  Código de muestra:

  ![](assets/sample-code.png)

+++

+++Implementación manual del SDK web

Consulte [Seguimiento de vínculos](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es) para obtener información sobre cómo implementar el seguimiento de vínculos y cómo activar Activity Map capturando el `region` del elemento HTML pulsado.

>[!NOTE]
>
>Al habilitar el seguimiento de vínculos con el SDK web, se envían eventos de vínculo cuando un cliente navega de una página a otra. Se trata de un funcionamiento diferente al de AppMeasurement y puede dar lugar a que se envíen más visitas facturables a Adobe. 

+++

+++Extensión de Analytics (etiquetas de Adobe Experience Platform)

En las etiquetas de Adobe Experience Platform, vaya a la propiedad para la que está implementando Analytics. En el cuadro de diálogo [!UICONTROL Instalar extensión], seleccione **[!UICONTROL Utilizar Activiy Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Descargue la última biblioteca de Javascript para AppMeasurement.
Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Administrador de códigos]**.
1. Impleméntelo siguiendo [estas instrucciones](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=es).

+++

## Paso 2. Habilitar los informes de Activity Map {#enable}

Es necesario habilitar los informes de Activity Map en el nivel de grupo de informes.

1. Inicie sesión en Adobe Analytics y vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Selecionar un grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]**.

1. Activity Map recopila los datos sobre vínculos en informes de Activity Map. Para que se realice la activación, primero debe activar las variables haciendo clic en **[!UICONTROL Habilitar los informes de Activity Map]**.

   En este paso se añaden todas las dimensiones de Analytics que se necesitan para recopilar datos.

   ![](assets/enable.png)

1. Cuando pase una hora más o menos, consulte el [informe Página de Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que muestra todas las páginas donde los usuarios han hecho clic en un vínculo.

## Paso 3. Añada usuarios al perfil del producto [!UICONTROL Activity Map Access] {#add_users}

1. Haga clic en **[!UICONTROL Añadir usuarios al grupo]**.

   Esto le llevará a la página de perfil del producto de [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Si no ha creado un perfil de producto [!UICONTROL Activity Map Access], hágalo ahora. Los elementos de permiso necesarios para este perfil son [!UICONTROL Herramientas de análisis] > [!UICONTROL Mapa de actividades] y [!UICONTROL Herramientas de análisis] > [!UICONTROL Publicación de segmentos].

1. Añada usuarios a ese perfil de producto. De este modo, sus usuarios podrán descargar Activity Map desde **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL ActivityMap]**.

