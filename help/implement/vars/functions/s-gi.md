---
title: s_gi()
description: Cree y rastree instancias de AppMeasurement.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# s_gi

La `s_gi()` función crea una instancia de AppMeasurement o la encuentra por ID del grupo de informes. AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. Si no existe una instancia, se crea una nueva.

## s_gi() en Adobe Experience Platform Launch

La extensión de Analytics crea una instancia del objeto de seguimiento y lo administra. Sin embargo, también puede establecer un objeto de seguimiento global en el acordeón Administración [!UICONTROL de] biblioteca al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón Administración [!UICONTROL de] biblioteca y seleccione cualquier botón de radio que no sea [!UICONTROL Administrar la biblioteca para mí].

El campo de texto de la variable global permite establecer un objeto de seguimiento personalizado. Its default value is `s`.

## s_gi() en el editor de código personalizado AppMeasurement e Launch

Llame a la `s_gi()` función para crear una instancia de un objeto de seguimiento. Su único argumento contiene una cadena delimitada por comas de ID de grupos de informes. Se requiere el argumento de la ID del grupo de informes.

> [!TIP] Adobe recomienda usar la `s` variable como objeto de seguimiento. Adobe utiliza `s` en su documentación, ejemplos de implementación y complementos. Sin embargo, puede utilizar cualquier variable siempre y cuando sea coherente en el sitio.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!WARNING] Las siguientes secciones y ejemplos contienen temas de implementación complejos. Pruebe exhaustivamente la implementación y rastree las personalizaciones importantes en el documento [de diseño de](../../prepare/solution-design.md)soluciones de su organización.

## Administrar varias implementaciones con diferentes objetos de seguimiento

Puede enviar diferentes datos a diferentes grupos de informes si crea instancias de varios objetos de seguimiento. Estos dos objetos de seguimiento funcionan de forma independiente entre sí.

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

## Restaure las variables de AppMeasurement después de sobrescribir el objeto s

Algunas herramientas de terceros también pueden utilizar el objeto JavaScript `s` . Si sobrescribe accidentalmente el `s` objeto del sitio, puede llamar `s_gi` con el mismo argumento de cadena RSID para restaurar todos los métodos y variables sobrescritos.

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

Si dos variables hacen referencia a la misma `s_gi()` función con el mismo grupo de informes, puede utilizar las variables de forma intercambiable.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
