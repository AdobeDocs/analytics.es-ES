---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
source-git-commit: 8e701a3da6f04ccf2d7ac3abd10c6df86feb00a7
workflow-type: ht
source-wordcount: '755'
ht-degree: 100%

---

# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe Analytics requiere código en el sitio web, la aplicación móvil u otra aplicación para enviar datos a los servidores de recopilación de datos. Hay varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

## Métodos de implementación de sitios web

Para su **sitio web**, están disponibles los siguientes métodos de implementación:

### Lado del cliente

* **Extensión del SDK web**: método estandarizado y recomendado de implementación de Adobe Analytics para nuevos clientes. Añada la **extensión de SDK web de Adobe Experience Platform** en las **Etiquetas** de la recopilación de datos de Adobe Experience Platform, y después coloque una etiqueta de carga en cada página. La etiqueta envía datos a la **red Edge** de Adobe Experience Platform, que reenvía esos datos a Adobe Analytics.
  ![Extensión del SDK web](./assets/websdk-extension-implementation.png)
Consulte [Implementación de Adobe Analytics con la extensión de SDK web de Adobe Experience Platform.](./aep-edge/overview.md) para obtener más información.

* **SDK web**: puede cargar manualmente las bibliotecas del SDK web en su sitio si no desea utilizar la recopilación de datos de Adobe Experience Platform. Haga referencia a la biblioteca del SDK web (`alloy.js`) en cada página y envíe las llamadas de seguimiento deseadas a la **red Edge** de Adobe Experience Platform en un formato conveniente para su organización. La red Edge reenvía esos datos a Adobe Analytics.
  ![SDK web](./assets/websdk-implementation.png)
Consulte [Implementación de Adobe Analytics con la extensión de SDK web de Adobe Experience Platform](./aep-edge/overview.md) para obtener más información.

* **Extensión de Analytics**: añada la **Extensión de Adobe Analytics** en las **Etiquetas** de recopilación de datos de Adobe Experience Platform, y después coloque una etiqueta de carga en cada página. La etiqueta envía datos directamente a Adobe Analytics. Utilice este método de implementación si desea aprovechar la comodidad de las etiquetas, pero no quiere recurrir a la infraestructura de la red Edge.
  ![Extensión de Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulte [Implementación de Adobe Analytics con la extensión de Analytics](launch/overview.md) para obtener más información.

* **JavaScript heredado:** método manual histórico para implementar Adobe Analytics. Haga referencia a la biblioteca AppMeasurement (`AppMeasurement.js`) en cada página y, a continuación, establezca las variables y la configuración utilizadas en JavaScript.
  ![Implementación de Adobe Analytics con JavaScript heredado](./assets/appmeasurement-implementation.png)
Este método de implementación puede ser útil para implementaciones que utilizan código personalizado y es ideal para tipos de implementación que no se ofrecen en ninguna otra parte, como para [Páginas AMP](other/amp.md).

El siguiente flujo de decisión puede ayudarle a seleccionar un método de implementación del lado del cliente:

![Un árbol de decisión para seleccionar un método de implementación, tal como se describe en esta sección.](./assets/decision-tree.png)


>[!TIP]
>
>Póngase en contacto con su equipo de cuentas de Adobe para obtener asesoramiento y prácticas recomendadas sobre qué implementación elegir en función de su situación actual.

### Del lado del servidor

Para implementar Adobe Analytics del lado del servidor, tiene las siguientes opciones:

* **API de Edge Network**: el código se implementa en el servidor que utiliza la API de Edge Network de Adobe Experience Platform para comunicarse con Adobe Analytics a través de una secuencia de datos.
  ![Implementación del lado del servidor](assets/edge-network-server-api.svg)
para obtener más información, consulte [Implementación de Adobe Analytics con la API de Edge Network en Adobe Experience Platform](/help/implement/aep-edge/api/overview.md).

* **API de inserción de datos (lote)**: las API de inserción de datos de Adobe Analytics (lote) se utilizan para recopilar datos del lado del servidor directamente en Adobe Analytics.
  ![API de inserción de datos](assets/analytics-apis.png)
Consulte [API de inserción de datos](../import/c-data-insertion-api/c-data-insertion-api.md) para obtener más información.

## Métodos de implementación de aplicaciones móviles

Para su **aplicación móvil**, están disponibles los siguientes métodos de implementación:

* **Extensión del SDK móvil**: método estandarizado y recomendado para implementar Adobe Analytics en su aplicación móvil. Use bibliotecas específicas para enviar fácilmente datos a Adobe desde su aplicación móvil. Añada la **Extensión de SDK móvil de Adobe Experience Platform** en las **Etiquetas** de la recopilación de datos de Adobe Experience Platform. A continuación, implemente la biblioteca del SDK móvil en la aplicación. Puede utilizar el SDK para importar bibliotecas, registrar extensiones y cargar la configuración de etiquetas. Envío de datos a la **Red Edge** de Adobe Experience Platform; a continuación, Edge reenvía esos datos a Adobe Analytics.
  ![Extensión del SDK móvil](./assets/mobilesdk-extension.png)

  Consulte [Implementar Adobe Analytics usando el SDK de Adobe Experience Platform Mobile](../implement/aep-edge/mobile-sdk/overview.md) para obtener más información.

* **Extensión de Analytics**: añada la **Extensión de Adobe Analytics** en las **Etiquetas** de la recopilación de datos de Adobe Experience Platform, e implemente la biblioteca del SDK móvil en la aplicación. Puede utilizar el SDK para importar bibliotecas, registrar extensiones y cargar la configuración de etiquetas. Este método de implementación envía datos directamente a Adobe Analytics. Se recomienda si desea la comodidad de la recopilación de datos de Adobe Experience Platform, pero no desea utilizar la infraestructura de red Edge de Experience Platform de Adobe.
  ![Extensión de Analytics](./assets/mobilesdk-analytics-extension.png)

  Consulte [Implementar Adobe Analytics usando la extensión de Analytics](../implement/aep-edge/mobile-sdk/overview.md) para obtener más información.


>[!CAUTION]
>
>Consulte los [Anuncios de fin de compatibilidad de SDK](https://developer.adobe.com/client-sdks/resources/sdks-end-of-support/) para obtener compatibilidad con versiones anteriores de los SDK móviles de Adobe.

## Artículos de implementación de Analytics clave

* [Ocuparse de una implementación de Adobe Analytics existente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creación de una propiedad de etiquetas en Experience Platform](launch/create-analytics-property.md)
* [Actualizaciones de AppMeasurement](appmeasurement-updates.md)
* [Tutorial sobre la configuración de Adobe Analytics con el SDK web de Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics.html?lang=es)
* [Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=es)


## Recursos clave de Analytics

* [Contactar con el servicio de atención al cliente](https://experienceleague.adobe.com/es?support-solution=Analytics?lang=es#support)
* [Comunidad de Adobe Analytics en Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es)
* [Recursos de Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=es)
* [Últimas notas de la versión](../release-notes/latest.md)
