---
title: linkType
description: Utilice la variable linkType para determinar a qué dimensión de seguimiento de vínculos pertenece la visita.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

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
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en Enviar señalización.
6. Haga clic en el botón de radio `s.tl()` que muestra la lista desplegable [!UICONTROL Tipo de vínculo].

Puede configurar este menú desplegable como [!UICONTROL Vínculo personalizado], [!UICONTROL Vínculo de descarga] o [!UICONTROL Vínculo de salida].

## s.linkType en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkType` es una cadena que acepta uno de los tres valores de un solo carácter: `o`, `d` o `e`. Si se llama un método `tl()` sin un tipo de vínculo, el valor predeterminado es Vínculo personalizado.

* `o` - Vínculos personalizados
* `d`: Vínculos de descarga
* `e`: Vínculos de salida

>[!TIP]
>
>Esta variable es el segundo parámetro del método `tl()` y no suele ser necesario configurarla como variable independiente. Sin embargo, puede utilizar la variable `linkType` si no desea establecer valores como argumentos en el método `tl()`.

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
