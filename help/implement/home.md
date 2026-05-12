---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/c1TZC9k-mu1n95Oq3jhQOvcBXFwx8oK28plhoNcJDK4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 197233b18a57ac67d4b56ddd34f296d88dd9c4b2
workflow-type: tm+mt
source-wordcount: 814
ht-degree: 83%

---

# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe Analytics requiere código en el sitio web, la aplicación móvil u otra aplicación para enviar datos a los servidores de recopilación de datos. Hay varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

## Métodos de implementación de sitios web

Para su **sitio web**, están disponibles los siguientes métodos de implementación:

### Lado del cliente

* **Extensión del SDK web**: método estandarizado y recomendado de implementación de Adobe Analytics para nuevos clientes. Añada la **extensión de SDK web de Adobe Experience Platform** en las **Etiquetas** de la recopilación de datos de Adobe Experience Platform, y después coloque una etiqueta de carga en cada página. La etiqueta envía datos a la **red Edge** de Adobe Experience Platform, que reenvía esos datos a Adobe Analytics.
  Extensión de ![Web SDK](./assets/websdk-extension-implementation.png)
Consulte [Cómo implementar Adobe Analytics con la extensión Adobe Experience Platform Web SDK.](./aep-edge/overview.md) para más información.

* **SDK web**: puede cargar manualmente las bibliotecas del SDK web en su sitio si no desea utilizar la recopilación de datos de Adobe Experience Platform. Haga referencia a la biblioteca del SDK web (`alloy.js`) en cada página y envíe las llamadas de seguimiento deseadas a la **red Edge** de Adobe Experience Platform en un formato conveniente para su organización. La red Edge reenvía esos datos a Adobe Analytics.
  ![Web SDK](./assets/websdk-implementation.png)
Consulte [Cómo implementar Adobe Analytics mediante Adobe Experience Platform Web SDK](./aep-edge/overview.md) para obtener más información.

* **Extensión de Analytics**: añada la **Extensión de Adobe Analytics** en las **Etiquetas** de recopilación de datos de Adobe Experience Platform, y después coloque una etiqueta de carga en cada página. La etiqueta envía datos directamente a Adobe Analytics. Utilice este método de implementación si desea aprovechar la comodidad de las etiquetas, pero no quiere recurrir a la infraestructura de la red Edge.
  Extensión ![Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulte [Cómo implementar Adobe Analytics con la extensión de Analytics](launch/overview.md) para obtener más información.

* **JavaScript heredado:** método manual histórico para implementar Adobe Analytics. Haga referencia a la biblioteca AppMeasurement (`AppMeasurement.js`) en cada página y, a continuación, establezca las variables y la configuración utilizadas en JavaScript.
  ![Cómo implementar Adobe Analytics mediante JavaScript heredado](./assets/appmeasurement-implementation.png)
Este método de implementación puede ser útil para implementaciones que usan código personalizado y es ideal para tipos de implementación que no se ofrecen en ninguna otra parte, como por ejemplo [páginas AMP](other/amp.md).

El siguiente flujo de decisión puede ayudarle a seleccionar un método de implementación del lado del cliente:

![Un árbol de decisión para seleccionar un método de implementación, tal como se describe en esta sección.](./assets/decision-tree.png)


>[!TIP]
>
>Póngase en contacto con su equipo de cuentas de Adobe para obtener asesoramiento y prácticas recomendadas sobre qué implementación elegir en función de su situación actual.

### Del lado del servidor

Para implementar Adobe Analytics del lado del servidor, tiene las siguientes opciones:

* **API de Edge Network**: el código se implementa en el servidor que utiliza la API de Edge Network de Adobe Experience Platform para comunicarse con Adobe Analytics a través de una secuencia de datos.
  ![Implementación del lado del servidor](assets/edge-network-server-api.png)
Consulte [Implementar Adobe Analytics mediante la API de Adobe Experience Platform Edge Network](/help/implement/aep-edge/api/overview.md) para obtener más información.

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
* [Tutorial sobre la configuración de Adobe Analytics con Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics.html?lang=es)
* [Tutorial de implementación de Adobe Experience Cloud en aplicaciones móviles](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=es)


## Recursos clave de Analytics

* [Póngase en contacto con el Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Analytics?lang=es#support)
* [Comunidad de Adobe Analytics en Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=es)
* [Recursos de Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=es)
* [Últimas notas de la versión](../release-notes/latest.md)
