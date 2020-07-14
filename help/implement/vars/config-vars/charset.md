---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 60%

---


# charSet

Adobe utiliza la variable charSet para convertir datos entrantes en UTF-8 para almacenamiento y generación de informes de Analytics. La mayoría de los sitios no necesitan establecer esta variable.

Configure esta variable solo si ve valores incorrectos ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) en los informes. Puede configurar esta variable página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en Adobe Experience Platform Launch

Conjunto de caracteres es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Conjunto de caracteres].

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Evite cambiar el valor de `UTF-8` a menos que vea valores distorsionados en los informes.

## s.charSet en el editor de código personalizado de AppMeasurement y Launch

La variable `charSet` es una cadena. Si tiene valores ilegibles en Adobe Analytics, establezca esta variable en el mismo valor que la etiqueta `<meta charset="">` HTML del sitio.

```js
s.charSet = "UTF-8";
```
