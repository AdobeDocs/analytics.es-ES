---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Adobe utiliza la variable charSet para convertir datos entrantes en UTF-8 para almacenamiento y generación de informes de Analytics. Si su sitio utiliza un charSet que no sea UTF-8, esta variable permite que Adobe codifique los datos correctamente. Esta variable se puede configurar página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en el lanzamiento de Adobe Experience Platform

Conjunto de caracteres es un campo bajo el acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General] , que muestra el campo Conjunto [!UICONTROL de] caracteres.

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Este valor debe coincidir con la codificación de caracteres del sitio. La mayoría de los sitios utilizan `UTF-8`.

## s.charSet en el editor de código personalizado AppMeasurement e Launch

La `charSet` variable es una cadena. Establezca esta variable en el mismo valor que la etiqueta `<meta charset="">` HTML del sitio.

```js
s.charSet = "UTF-8";
```
