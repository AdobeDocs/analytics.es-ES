---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# charSet

Adobe utiliza la variable charSet para convertir datos entrantes en UTF-8 para almacenamiento y generación de informes de Analytics. La mayoría de los sitios no necesitan establecer esta variable.

Establezca esta variable solo si observa valores ilegibles ([mojibake](https://es.wikipedia.org/wiki/Mojibake)) en los informes. Esta variable se puede configurar página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en Adobe Experience Platform Launch

Conjunto de caracteres es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Conjunto de caracteres].

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Evite cambiar el valor de `UTF-8` a menos que vea valores ilegibles en los informes.

## s.charSet en el editor de código personalizado de AppMeasurement y Launch

La variable `charSet` es una cadena. Si tiene valores ilegibles en Adobe Analytics, establezca esta variable con el mismo valor que la etiqueta HTML `<meta charset="">` del sitio.

```js
s.charSet = "UTF-8";
```
