---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: b157674adf67fa6ef0f2e75775d0ec888cff3cba
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 55%

---

# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe requiere código en su sitio o aplicación para enviar datos a los servidores de recopilación de datos de Adobe. Los pasos siguientes indican cómo funciona una implementación típica.

1. Cuando un visitante llega a su sitio, se realiza una solicitud al servidor web.
2. El servidor web del sitio envía la información de código de página, y se muestra la página en el explorador.
3. Se carga la página, y se ejecuta el código JavaScript de Analytics.
El código JavaScript envía una solicitud de imagen a los servidores de recopilación de datos de Adobe. Los datos de página definidos en la implementación se envían como parte de una cadena de consulta en esta solicitud de imagen.

4. Adobe devuelve una imagen en píxeles transparente.
5. Los servidores de Adobe almacenan los datos recopilados en uno o más *grupos de informes*.
6. Los datos de grupos de informes rellenan los informes a los que se puede tener acceso en un explorador web.

La ejecución de código JavaScript ocurre rápidamente y no afecta visiblemente a los tiempos de carga de una página. Este método permite contabilizar páginas que se mostraron cuando un visitante hizo clic en **[!UICONTROL Recarga]** o **[!UICONTROL Atrás]** para alcanzar una página, porque el JavaScript se ejecuta incluso cuando se recupera la página de la memoria caché.

Adobe Analytics requiere código en el sitio web, la aplicación móvil u otra aplicación para enviar datos a los servidores de recopilación de datos. Hay varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

## Métodos de implementación de sitios web

Para su **sitio web**, están disponibles los siguientes métodos de implementación:

* **Extensión del SDK web**: método estandarizado y recomendado de implementación de Adobe Analytics para nuevos clientes. Añada el **Extensión de SDK web de Adobe Experience Platform** en la recopilación de datos de Adobe Experience Platform **Etiquetas**, luego coloque una etiqueta de carga en cada página. La etiqueta de envía datos a Adobe Experience Platform **Red perimetral**, que reenvía esos datos a Adobe Analytics.
  ![Extensión de SDK web](./assets/websdk-extension-implementation.png)
Consulte [Cómo implementar Adobe Analytics con la extensión SDK para web de Adobe Experience Platform.](./aep-edge/overview.md) para obtener más información.

* **SDK web**: puede cargar manualmente las bibliotecas del SDK web en su sitio si no desea utilizar la recopilación de datos de Adobe Experience Platform. Haga referencia a la biblioteca del SDK web (`alloy.js`) en cada página y envíe las llamadas de seguimiento deseadas a la **red Edge** de Adobe Experience Platform en un formato conveniente para su organización. La red perimetral reenvía esos datos a Adobe Analytics.
  ![SDK web](./assets/websdk-implementation.png)
Consulte [Implementación de Adobe Analytics mediante el SDK web de Adobe Experience Platform](./aep-edge/overview.md) para obtener más información.

* **Extensión de Analytics**: Añada el **Extensión de Adobe Analytics** en la recopilación de datos de Adobe Experience Platform **Etiquetas**, luego coloque una etiqueta de carga en cada página. La etiqueta envía datos directamente a Adobe Analytics. Utilice este método de implementación si desea la comodidad de las etiquetas, pero no desea utilizar la infraestructura de red perimetral.
  ![Extensión de Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulte [Implementación de Adobe Analytics con la extensión de Analytics](launch/overview.md) para obtener más información.

* **JavaScript heredado:** método manual histórico para implementar Adobe Analytics. Haga referencia a la biblioteca de AppMeasurement (`AppMeasurement.js`) en cada página y, a continuación, establezca las variables y la configuración en JavaScript.
  ![Implementación de Adobe Analytics con JavaScript heredado](./assets/appmeasurement-implementation.png)
Este método de implementación puede ser útil para implementaciones que utilizan código personalizado y es ideal para tipos de implementación que no se ofrecen en ninguna otra parte, como para [Páginas AMP](other/amp.md).

El siguiente flujo de decisión puede ayudarle a seleccionar un método de implementación:

![Un árbol de decisión para seleccionar un método de implementación, tal como se describe en esta sección.](./assets/decision-tree.png)


>[!TIP]
>
>Póngase en contacto con el equipo de cuenta de Adobe para obtener asesoramiento y prácticas recomendadas sobre la implementación que debe elegir en función de su situación actual.

## Métodos de implementación de aplicaciones móviles

Para su **aplicación móvil**, están disponibles los siguientes métodos de implementación:

* **Extensión del SDK móvil**: método estandarizado y recomendado para implementar Adobe Analytics en su aplicación móvil. Use bibliotecas específicas para enviar fácilmente datos a Adobe desde su aplicación móvil. Añada el **Extensión de SDK móvil de Adobe Experience Platform** en la recopilación de datos de Adobe Experience Platform **Etiquetas** A continuación, implemente la biblioteca del SDK móvil en la aplicación. Puede utilizar el SDK para importar bibliotecas, registrar extensiones y cargar la configuración de etiquetas. Envío de datos a Adobe Experience Platform **Red perimetral**; A continuación, Edge reenvía esos datos a Adobe Analytics.
  ![Extensión del SDK móvil](./assets/mobilesdk-extension.png)

  Consulte [Implementar Adobe Analytics usando el SDK de Adobe Experience Platform Mobile](../implement/aep-edge/mobile-sdk/overview.md) para obtener más información.

* **Extensión de Analytics**: Añada el **Extensión de Adobe Analytics** en la recopilación de datos de Adobe Experience Platform **Etiquetas**e implemente la biblioteca del SDK móvil en la aplicación. Puede utilizar el SDK para importar bibliotecas, registrar extensiones y cargar la configuración de etiquetas. Este método de implementación envía datos directamente a Adobe Analytics. Se recomienda si desea la comodidad de la recopilación de datos de Adobe Experience Platform, pero no desea utilizar la infraestructura de red de Experience Platform Edge de Adobe.
  ![Extensión de Analytics](./assets/mobilesdk-analytics-extension.png)

  Consulte [Implementar Adobe Analytics usando la extensión de Analytics](../implement/aep-edge/mobile-sdk/overview.md) para obtener más información.


>[!CAUTION]
>
>La compatibilidad con los SDK Mobile de la versión 4 finalizó el 31 de agosto de 2021. Consulte [las preguntas frecuentes sobre el fin de la compatibilidad de los SDK móviles de la versión 4](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/v4-faq/) para obtener más información.

## Artículos de implementación de Analytics clave

* [Ocuparse de una implementación de Adobe Analytics existente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creación de una propiedad de etiquetas en Experience Platform](launch/create-analytics-property.md)
* [Actualizaciones de AppMeasurement](appmeasurement-updates.md)

## Más guías del usuario de Analytics

[Guías del usuario de Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=es)

## Recursos clave de Analytics

* [Contactar con el servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=es#support)
* [Foro de Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es)
* [Recursos de Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=es)
