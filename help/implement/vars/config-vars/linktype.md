---
title: linkType
description: Utilice la variable linkType para determinar a qué dimensión de seguimiento de vínculos pertenece la visita.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

Las visitas de seguimiento de vínculos pueden completar una de las tres dimensiones:

* Vínculos personalizados
* Vínculos de salida
* Vínculos de descarga

Utilice la `linkType` variable para determinar qué dimensión desea rellenar al ejecutar la siguiente `tl()` función.

## Tipo de vínculo en Adobe Experience Platform Launch

Configure el tipo de vínculo al configurar una regla para enviar una señalización.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono &#39;+&#39;
5. Defina la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en Enviar señalización.
6. Haga clic en el `s.tl()` botón de opción que muestra la lista desplegable Tipo [!UICONTROL de] vínculo.

Puede establecer este menú desplegable en Vínculo personalizado, Vínculo [!UICONTROL de]descarga o Vínculo [!UICONTROL de]salida.

## s.linkType en el editor de código personalizado AppMeasurement e Launch

La `s.linkType` variable es una cadena que acepta uno de los tres valores de un solo carácter: `o`, `d`o `e`. Si se llama a una `tl()` función sin un tipo de vínculo, el valor predeterminado es Vínculo personalizado.

* `o` - Vínculos personalizados
* `d` - Vínculos de descarga
* `e` - Vínculos de salida

> [!TIP] Esta variable es el segundo parámetro de la `tl()` función y no suele ser necesario configurarla como variable independiente. Sin embargo, puede utilizar la `linkType` variable si no desea establecer valores como argumentos en la `tl()` función.

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
