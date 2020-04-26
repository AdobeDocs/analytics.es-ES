---
title: linkName
description: Configure el nombre de la visita del vínculo personalizado.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

Si esta variable está en blanco, AppMeasurement vuelve a la variable [`linkURL`](linkurl.md).

## Nombre del vínculo en Adobe Experience Platform Launch

Puede definir el campo de nombre del vínculo al configurar una regla para enviar una señalización.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en Enviar señalización.
6. Haga clic en el botón de opciones `s.tl()` que muestra el campo [!UICONTROL Nombre del vínculo].

## s.linkName en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkName` es una cadena que determina el valor de dimensión de los vínculos personalizados, de descarga o de salida (según lo que sea [`s.linkType`](linktype.md)). Puede contener hasta 100 bytes.

>[!TIP] Esta variable es el tercer parámetro del `tl()` método y no suele ser necesario configurarla como variable independiente. However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
