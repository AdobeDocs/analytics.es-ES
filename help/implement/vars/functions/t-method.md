---
title: t
description: Envíe una llamada de seguimiento de vista de página a Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 56%

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
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

Adobe recibe la solicitud de imagen y, a continuación, analiza los parámetros de encabezado, dirección URL y cadena de consulta de la solicitud. Los servidores de recopilación de datos devuelven una imagen transparente de 1x1 píxeles, que se muestra de forma invisible en el sitio.

## Envío de eventos con la extensión Web SDK

Utilice una acción para configurar el envío de datos de evento XDM a Adobe. La secuencia de datos recibe estos datos, aplica todas las asignaciones configuradas y reenvía esos datos a Adobe Analytics si es un servicio agregado a esa secuencia de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en la acción que desee o en el icono **&#39;+&#39;** para agregar una acción.
1. Establezca la lista desplegable [!UICONTROL Extension] en **[!UICONTROL Adobe Experience Platform Web SDK]** y el [!UICONTROL Tipo de acción] en **[!UICONTROL Enviar evento]**.

## Enviar evento manualmente implementando Web SDK

Utilice el comando `sendEvent` para enviar datos a Adobe. La secuencia de datos recibe estos datos, aplica todas las asignaciones configuradas y reenvía esos datos a Adobe Analytics si es un servicio agregado a esa secuencia de datos.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Consulte [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) en la documentación de Web SDK para obtener más información.

## Llamada de seguimiento de vista de página mediante la extensión Adobe Analytics

La extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform tiene una ubicación dedicada configurada como una llamada de seguimiento de vista de página.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
1. En [!UICONTROL Acciones], haga clic en la acción que desee o en el icono **&#39;+&#39;** para agregar una acción.
1. Establezca la lista desplegable [!UICONTROL Extension] en **[!UICONTROL Adobe Analytics]** y [!UICONTROL Action Type] en **[!UICONTROL Send Beacon]**.
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
