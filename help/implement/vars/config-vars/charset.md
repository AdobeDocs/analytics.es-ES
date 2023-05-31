---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: ef82c34f97a0c8172f097b83b521860a1897c82c
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 66%

---

# charSet

El `charSet` El Adobe utiliza la variable para convertir datos entrantes a UTF-8 para almacenamiento y generación de informes de Analytics. La mayoría de los sitios no necesitan establecer esta variable.

Establezca esta variable solo si observa valores ilegibles ([mojibake](https://es.wikipedia.org/wiki/Mojibake)) en los informes. Esta variable se puede configurar página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en el SDK web

Actualmente, el SDK web solo admite UTF-8 y no proporciona opciones para cambiar la codificación.

## Conjunto de caracteres en la extensión de Adobe Analytics

Conjunto de caracteres es un campo en la variable [!UICONTROL General] al configurar la extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Conjunto de caracteres].

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Evite cambiar el valor de `UTF-8` a menos que vea valores ilegibles en los informes.

## s.charSet en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `charSet` es una cadena. Si tiene valores ilegibles en Adobe Analytics, establezca esta variable con el mismo valor que la etiqueta HTML `<meta charset="">` del sitio.

```js
s.charSet = "UTF-8";
```
