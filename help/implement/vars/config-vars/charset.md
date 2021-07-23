---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 90%

---

# charSet

Adobe utiliza la variable charSet para convertir datos entrantes en UTF-8 para almacenamiento y generación de informes de Analytics. La mayoría de los sitios no necesitan establecer esta variable.

Establezca esta variable solo si observa valores ilegibles ([mojibake](https://es.wikipedia.org/wiki/Mojibake)) en los informes. Esta variable se puede configurar página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en Adobe Experience Platform

Conjunto de caracteres es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Vaya a `experience.adobe.com` e inicie sesión cuando se le solicite.
1. Seleccione [!UICONTROL Iniciar / Recopilación de datos].
1. Haga clic en [!UICONTROL Ir a Launch / Data Collection] y seleccione [!UICONTROL Etiquetas].
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Conjunto de caracteres].

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Evite cambiar el valor de `UTF-8` a menos que vea valores ilegibles en los informes.

## s.charSet en el editor de código personalizado de AppMeasurement y 

La variable `charSet` es una cadena. Si tiene valores ilegibles en Adobe Analytics, establezca esta variable con el mismo valor que la etiqueta HTML `<meta charset="">` del sitio.

```js
s.charSet = "UTF-8";
```
