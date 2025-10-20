---
title: Identificación de visitantes con AppMeasurement
description: Identifique correctamente a los visitantes al implementar Adobe Analytics mediante AppMeasurement.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Identificación de visitantes con AppMeasurement

AppMeasurement es la biblioteca JavaScript heredada de Adobe Analytics para la recopilación de datos. Aunque AppMeasurement por sí solo ofrece una forma nativa de identificar a los visitantes, muchos exploradores modernos rechazan las cookies de terceros que intenta configurar. Adobe recomienda encarecidamente utilizar el servicio de ID de visitante de Adobe Experience Cloud en todas las implementaciones para cumplir con los estándares modernos de privacidad del explorador. Todas las versiones de AppMeasurement vienen empaquetadas con `VisitorAPI.js`, la biblioteca de JavaScript utilizada para implementar el servicio de ID de visitante.

## Identificación de visitantes mediante el servicio de ID de visitante (recomendado)

Asegúrese de que está preparado con lo siguiente:

* Descargar [la versión más reciente de AppMeasurement](https://github.com/adobe/appmeasurement). La biblioteca descargada incluye `AppMeasurement.js` y `VisitorAPI.js`.
* Un [ID del grupo de informes](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) de desarrollo.
* El dominio perimetral deseado para [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Su ID de organización de IMS:
   1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com) con sus credenciales de Adobe ID.
   1. En cualquier lugar de la interfaz de Experience Cloud, presione `[Cmd]` + `[I]` (iOS) o `[Ctrl]` + `[I]` (Windows).
   1. Aparece un **[!UICONTROL depurador de datos de usuario]**. Seleccione la ficha **[!UICONTROL Organizaciones asignadas]**.
   1. Expanda la organización IMS deseada.
   1. Busque el campo **[!UICONTROL ID]**.

Una vez que tenga los recursos anteriores, la siguiente página de ejemplo básica contiene las llamadas mínimas requeridas para enviar datos a Adobe Analytics:

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>Puede realizar un seguimiento de si una visita usa el servicio de identificación del visitante asignando la presencia de `Visitor` a una variable personalizada en [`doPlugins`](/help/implement/vars/functions/doplugins.md):
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identificación de visitantes mediante la cookie `s_vi` (no recomendado)

>[!IMPORTANT]
>
>Adobe recomienda evitar este método para identificar a los visitantes.

Si su organización no utiliza el servicio de ID de visitante, AppMeasurement utiliza su propia forma de identificación. Cuando un visitante llega a su sitio por primera vez, la biblioteca comprueba la existencia de una cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Esta cookie se establece en el dominio que coincide con [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (para HTTPS) o [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (para HTTP).

* Si participa en el [programa de certificados administrados](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), su servidor de seguimiento sería normalmente un dominio de origen, por lo que las cookies de `s_vi` serían de origen.
* Si no participa en el programa de certificados administrados, el servidor de seguimiento suele ser un subdominio de `adobedc.net`, `omtrdc.net` o `2o7.net`, por lo que la cookie `s_vi` se convierte en una cookie de terceros. Debido a los estándares modernos de privacidad del explorador, la mayoría de los exploradores rechazan las cookies de terceros. Una vez rechazado, AppMeasurement intenta establecer una cookie de reserva (`fid`) de origen en su lugar.

Si establece `trackingServerSecure` correctamente, no se requieren más medidas de identificación del visitante.

## Identificación de visitantes que utilizan `visitorID` (no recomendado)

>[!IMPORTANT]
>
>Adobe recomienda evitar este método para identificar a los visitantes.

El uso de la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) permite que su organización complete el control independiente que identifica a los visitantes. Si usa `visitorID`, tenga en cuenta las siguientes limitaciones:

* Cada visita debe contener el mismo valor `visitorID` para que pueda contarse como un solo visitante.
   * Cualquier visita que omita `visitorID` intentará automáticamente usar otro método de identificación de visitante, tratándolo como un visitante separado.
   * Cualquier visita que contenga un valor `visitorID` diferente de una visita anterior se tratará como un visitante independiente.
   * Adobe no ofrece ninguna forma de unir las visitas con distintos ID de visitante.
* Las audiencias compartidas, Analytics para Target y los atributos del cliente no son compatibles con los visitantes identificados mediante `visitorID`.

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obtener instrucciones de implementación mediante esta variable.
