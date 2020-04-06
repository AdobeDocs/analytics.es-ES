---
title: linkType
description: Utilice la variable linkType para determinar a qué dimensión de seguimiento de vínculos pertenece la visita.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

Las visitas de seguimiento de vínculos pueden completar una de las tres dimensiones:

* Vínculos personalizados
* Vínculos de salida
* Vínculos de descarga

Utilice la variable `linkType` para determinar qué dimensión desea rellenar al ejecutar la siguiente función [`tl()`](../functions/tl-method.md).

## Tipo de vínculo en Adobe Experience Platform Launch

Establezca el tipo de vínculo al configurar una regla para enviar una señalización.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

Puede establecer este menú desplegable en [!UICONTROL Custom Link], [!UICONTROL Download Link]o [!UICONTROL Exit Link].

## s.linkType en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkType` es una cadena que acepta uno de los tres valores de un solo carácter: `o`, `d` o `e`. If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - Vínculos personalizados
* `d`: Vínculos de descarga
* `e`: Vínculos de salida

>[!TIP] Esta variable es el segundo parámetro del `tl()` método y no suele ser necesario configurarla como variable independiente. However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## Ejemplo

Las dos llamadas de seguimiento de vínculos de ejemplo siguientes son idénticas a nivel funcional. Son métodos diferentes para realizar la misma visita de seguimiento de vínculos.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
