---
title: t
description: Envíe una llamada de seguimiento de vista de página a Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '276'
ht-degree: 100%

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

## Llamada de seguimiento de vista de página mediante etiquetas en Adobe Experience Platform

La IU de recopilación de datos tiene una ubicación dedicada configurada como una llamada de seguimiento de vista de página.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en Enviar señalización.
6. Haga clic en el botón de opción `s.t()`.

## El método s.t() en el editor de código personalizado de AppMeasurement y 

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
