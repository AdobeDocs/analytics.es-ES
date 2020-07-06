---
title: linkName
description: Configure el nombre de la visita del vínculo personalizado.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---


# linkName

Utilice la variable `linkName` para determinar el valor de dimensión de los vínculos personalizados, de descarga o de salida al ejecutar el siguiente método [`tl()`](../functions/tl-method.md).

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

>[!TIP]
>
>Esta variable es el tercer parámetro del método `tl()` y no suele ser necesario configurarla como variable independiente. Sin embargo, puede utilizar la variable `linkName` si no desea establecer valores como argumentos en el método `tl()`.

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
