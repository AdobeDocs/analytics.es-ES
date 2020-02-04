---
title: linkName
description: Configure el nombre de la visita del vínculo personalizado.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkName

Utilice la `linkName` variable para determinar el valor de dimensión de los vínculos personalizados, de descarga o de salida al ejecutar la siguiente `tl()` función.

Si esta variable está en blanco, AppMeasurement vuelve a la `linkURL` variable.

## Nombre del vínculo en Adobe Experience Platform Launch

Puede definir el campo de nombre del vínculo al configurar una regla para enviar una señalización.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono &#39;+&#39;
5. Defina la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en Enviar señalización.
6. Haga clic en el `s.tl()` botón de radio que muestra el campo Nombre [!UICONTROL del] vínculo.

## s.linkName en AppMeasurement e inicie el editor de código personalizado

La `s.linkName` variable es una cadena que determina el valor de dimensión de los vínculos personalizados, de descarga o de salida (según lo que `s.linkType` sea). Puede contener hasta 100 bytes.

> [!TIP] Esta variable es el tercer parámetro de la `tl()` función y no suele ser necesario configurarla como variable independiente. Sin embargo, puede utilizar la `linkName` variable si no desea establecer valores como argumentos en la `tl()` función.

```js
s.linkName = "Example custom link";
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
