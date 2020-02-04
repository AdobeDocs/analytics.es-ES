---
title: Solución de problemas de implementaciones de código H
description: Conozca algunos problemas comunes con las implementaciones de JavaScript heredadas.
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Solución de problemas de implementaciones de código H

A continuación se indican los pasos para la resolución de problemas específicos de las implementaciones de código H.

## Incluir código de Analytics en la etiqueta Head

> [!NOTE] Aunque las implementaciones de código H requieren que se haga referencia al código en la `<body>` etiqueta , otras implementaciones (como el uso de Adobe Experience Platform Launch) requieren que se haga referencia al código en la `<head>` etiqueta .

El código de Analytics crea una imagen de 1x1 píxeles invisible. Anteriormente, una práctica común de implementación era colocar la `s_code.js` referencia en la `<head>` etiqueta . Colocar el código aquí evitó que la imagen afectara el diseño de la página de alguna manera. También se ejecuta antes, lo que le permite contar las vistas de página para cargas de página parciales de forma más eficaz.

However, certain elements of the code require the existence of the `<body>` object. Si el código JavaScript de Analytics está en la `<head>` etiqueta , se ejecuta antes de que exista el `<body>` objeto. As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. Colocar la referencia de secuencia de comandos `s_code.js` en la `<head>` etiqueta funciona, pero el resultado es una versión muy limitada de Analytics.

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Adobe recomienda colocar el código de Analytics lo más cerca posible de la parte superior de la `<body>` etiqueta. Asegúrese de que todas las variables de página se establecen después de que se cargue el `s_code.js` archivo.

> [!TIP] Si desea integrar Adobe Analytics con Adobe Target, el archivo de inclusión JavaScript debe colocarse en la parte inferior de la página.
