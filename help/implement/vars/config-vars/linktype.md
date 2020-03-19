---
title: linkType
description: Utilice la variable linkType para determinar a qué dimensión de seguimiento de vínculos pertenece la visita.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkType

Las visitas de seguimiento de vínculos pueden completar una de las tres dimensiones:

* Vínculos personalizados
* Vínculos de salida
* Vínculos de descarga

Utilice la `linkType` variable para determinar qué dimensión desea rellenar al ejecutar la siguiente [`tl()`](../functions/tl-method.md) función.

## Tipo de vínculo en Adobe Experience Platform Launch

Configure el tipo de vínculo al configurar una regla para enviar una señalización.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Rules] ficha y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Actions], haga clic en el icono &#39;+&#39;
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el [!UICONTROL Action Type] en Enviar señalización.
6. Haga clic en el `s.tl()` botón de opción que muestra la [!UICONTROL Link Type] lista desplegable.

Puede establecer este menú desplegable en [!UICONTROL Custom Link], [!UICONTROL Download Link]o [!UICONTROL Exit Link].

## s.linkType en el editor de código personalizado AppMeasurement e Launch

La `s.linkType` variable es una cadena que acepta uno de los tres valores de un solo carácter: `o`, `d`o `e`. Si se llama a un `tl()` método sin un tipo de vínculo, el valor predeterminado es Vínculo personalizado.

* `o` - Vínculos personalizados
* `d` - Vínculos de descarga
* `e` - Vínculos de salida

> [!TIP] Esta variable es el segundo parámetro del `tl()` método y no suele ser necesario configurarla como variable independiente. Sin embargo, puede utilizar la `linkType` variable si no desea establecer valores como argumentos en el `tl()` método.

```js
s.linkType = "e";
```

## Ejemplo

Las dos llamadas de seguimiento de vínculos de ejemplo siguientes son funcionalmente idénticas. Son métodos diferentes para realizar la misma visita de seguimiento de vínculos.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
