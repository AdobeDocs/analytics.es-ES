---
title: t
description: Envíe una llamada de seguimiento de vista de página a Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 57%

---

# t()

El método `t()` es un componente principal importante de Adobe Analytics. Toma todas las variables de Analytics definidas en la página, las compila en una solicitud de imagen y envía esos datos a los servidores de recopilación de datos de Adobe.

Por ejemplo, considere el siguiente código JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

La ejecución del método `t()` toma todas las variables de Analytics definidas y formula una URL basada en dichas variables. Algunas variables de Analytics determinan la dirección URL de la imagen, mientras que otras variables determinan los valores de parámetro de la cadena de consulta.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe recibe la solicitud de imagen y, a continuación, analiza los parámetros de encabezado, dirección URL y cadena de consulta de la solicitud. Los servidores de recopilación de datos devuelven una imagen transparente de 1x1 píxeles, que se muestra de forma invisible en el sitio.

## Envío de un evento mediante la extensión del SDK web

Utilice una acción para configurar el envío de datos de evento XDM a Adobe. El Datastream recibe estos datos, aplica cualquier asignación configurada y reenvía esos datos a Adobe Analytics si se trata de un servicio agregado a ese Datastream.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en la acción que desee o haga clic en la **&#39;+&#39;** para añadir una acción.
1. Configure las variables [!UICONTROL Extensión] lista desplegable a **[!UICONTROL SDK web de Adobe Experience Platform]** y [!UICONTROL Tipo de acción] a **[!UICONTROL Enviar evento]**.

## Envío manual de un evento de implementación del SDK web

Utilice la variable `sendEvent` para enviar datos a Adobe. El Datastream recibe estos datos, aplica cualquier asignación configurada y reenvía esos datos a Adobe Analytics si se trata de un servicio agregado a ese Datastream.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Consulte [Seguimiento de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es) en la documentación del SDK web para obtener más información.

## Llamada de seguimiento de vista de página mediante la extensión Adobe Analytics

La extensión Adobe Analytics de la recopilación de datos de Adobe Experience Platform tiene una ubicación dedicada configurada como llamada de seguimiento de vista de página.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en la acción que desee o haga clic en la **&#39;+&#39;** para añadir una acción.
1. Configure las variables [!UICONTROL Extensión] lista desplegable a **[!UICONTROL Adobe Analytics]** y [!UICONTROL Tipo de acción] a **[!UICONTROL Send Beacon]**.
1. Haga clic en el botón de opción `s.t()`.

## El método s.t() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame al método `s.t()` cuando desee enviar una llamada de seguimiento a Adobe.

```js
s.t();
```

Opcionalmente, puede utilizar un objeto como argumento para anular los valores de las variables. Consulte las [anulaciones de variables](../../js/overrides.md) para obtener más información.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Las versiones anteriores de AppMeasurement usaban varias líneas de código para llamar a esta función. Históricamente, el código adicional acomodaba soluciones alternativas para distintos exploradores. La estandarización y las prácticas recomendadas en los navegadores modernos ya no requieren este bloque de código. Ahora solo se necesita la llamada al método `s.t()`.
