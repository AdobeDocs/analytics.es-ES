---
title: t
description: Envíe una llamada de seguimiento de vista de página a Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# t()

El `t()` método es un componente principal importante de Adobe Analytics. Toma todas las variables de Analytics definidas en la página, las compila en una solicitud de imagen y envía esos datos a los servidores de recopilación de datos de Adobe.

Por ejemplo, considere el siguiente código JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

La ejecución del `t()` método toma todas las variables de Analytics definidas y formula una URL basada en dichas variables. Algunas variables de Analytics determinan la dirección URL de la imagen, mientras que otras variables determinan los valores de parámetro de la cadena de consulta.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe recibe la solicitud de imagen y, a continuación, analiza los parámetros de encabezado, dirección URL y cadena de consulta de la solicitud. Los servidores de recopilación de datos devuelven una imagen transparente de 1x1 píxeles, que se muestra de forma invisible en el sitio.

## Llamada de seguimiento de vista de página en Adobe Experience Platform Launch

Launch tiene una ubicación dedicada establecida una llamada de seguimiento de vista de página.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Rules] ficha y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Actions], haga clic en el icono &#39;+&#39;
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el [!UICONTROL Action Type] en Enviar señalización.
6. Click the `s.t()` radio button.

## s.t() en el editor de código personalizado AppMeasurement e Launch

Llame al `s.t()` método cuando desee enviar una llamada de seguimiento a Adobe.

```js
s.t();
```

Opcionalmente, puede utilizar un objeto como argumento para anular los valores de las variables. Consulte las sobrescrituras [de variables](../../js/overrides.md) para obtener más información.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] Las versiones anteriores de AppMeasurement usaban varias líneas de código para llamar a esta función. El código adicional acomodaba históricamente soluciones alternativas para distintos exploradores. La estandarización y las prácticas recomendadas en los navegadores modernos ya no requieren este bloque de código. Ahora solo `s.t()` se necesita la llamada de método.
