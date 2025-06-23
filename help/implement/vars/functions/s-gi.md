---
title: s_gi()
description: Cree y rastree instancias de AppMeasurement.
feature: Appmeasurement Implementation
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# s_gi

La función `s_gi()` crea una instancia de AppMeasurement o la encuentra por el ID del grupo de informes. AppMeasurement realiza un seguimiento de todas las instancias que se crean y `s_gi()` devuelve la instancia de un grupo de informes, si existe. Si no existe, se crea una nueva instancia.

## Creación de una instancia de un objeto de seguimiento con la extensión SDK web

La extensión SDK de Analytics crea una instancia del objeto de seguimiento y lo administra. Sin embargo, puede personalizar el nombre del objeto de seguimiento en la configuración de la extensión:

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** bajo el SDK web de Adobe Analytics.
1. Cambie el campo [!UICONTROL Nombre] al valor deseado. Su valor predeterminado es `alloy`.

## Creación de una instancia de un objeto de seguimiento implementando manualmente el SDK web

El siguiente código carga el SDK web y crea una instancia de un objeto de seguimiento. Puede personalizar el nombre del objeto de seguimiento cambiando la cadena `"alloy"` al final del script en línea al valor deseado.

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

Consulte [Instalación del SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=es) en la documentación del SDK web para obtener más información.

## Creación de una instancia de un objeto de seguimiento con la extensión de Adobe Analytics

La extensión de Analytics crea una instancia del objeto de seguimiento y lo administra. Sin embargo, también puede establecer un objeto de seguimiento global en el acordeón de [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Administración de biblioteca] y seleccione cualquier botón de opción que no sea [!UICONTROL Administrar la biblioteca por mí].

El campo de texto de la variable global permite establecer un objeto de seguimiento personalizado. Su valor predeterminado es `s`.

## s_gi() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame a la función `s_gi()` para crear una instancia de un objeto de seguimiento. Su único argumento contiene una cadena delimitada por comas de ID de grupos de informes. Se requiere el argumento del ID del grupo de informes.

>[!TIP]
>
>Adobe recomienda usar la variable `s` como objeto de seguimiento. Adobe utiliza `s` en su documentación, ejemplos de implementación y complementos. Sin embargo, puede utilizar cualquier variable siempre y cuando sea coherente en el sitio.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Las siguientes secciones y ejemplos contienen temas de implementación complejos. Pruebe exhaustivamente la implementación y rastree las personalizaciones importantes en el [documento de diseño de soluciones ](../../prepare/solution-design.md)de su organización.

## Administrar varias implementaciones con diferentes objetos de seguimiento

Puede enviar diferentes datos a varios grupos de informes si crea instancias de varios objetos de seguimiento. Estos dos objetos de seguimiento funcionan de forma independiente entre sí.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Restaure las variables de AppMeasurement después de sobrescribir el objeto “s”

Algunas herramientas de terceros también pueden utilizar el objeto `s` de JavaScript. Si sobrescribe accidentalmente el objeto `s` del sitio, puede llamar a `s_gi` con el mismo argumento de cadena de RSID para restaurar todos los métodos y variables sobrescritos.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Hacer referencia al mismo objeto de seguimiento con varias variables

Si dos variables hacen referencia a la misma función `s_gi()` con el mismo grupo de informes, puede utilizar las variables de forma intercambiable.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
