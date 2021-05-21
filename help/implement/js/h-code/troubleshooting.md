---
title: Solución de problemas de implementaciones de código H
description: Descubra algunos problemas comunes con las implementaciones de JavaScript heredadas.
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '244'
ht-degree: 100%

---

# Solución de problemas de implementaciones de código H

A continuación se indican los pasos para la resolución de problemas específicos de las implementaciones de código H.

## Incluir código de Analytics en la etiqueta Head

>[!NOTE]
>
>Aunque las implementaciones de código H requieren que se haga referencia al código en la etiqueta `<body>`, otras implementaciones (como el uso de Adobe Experience Platform Launch) requieren que se haga referencia al código en la etiqueta `<head>`.

El código de Analytics crea una imagen de 1x1 píxeles invisible. Anteriormente, una práctica común de implementación era colocar la referencia a `s_code.js` en la etiqueta `<head>`. Colocar el código aquí evitaba que la imagen afectara al diseño de la página de alguna manera. Esto se ejecuta antes, lo que optimiza el recuento de las vistas de página para cargas de página parciales.

Sin embargo, algunos elementos del código requieren que el objeto `<body>` esté presente. Si el código JavaScript de Analytics está en la etiqueta `<head>`, se ejecuta antes de que exista el objeto `<body>`. Como resultado, la implementación no recopila datos de [!UICONTROL ClickMap] y el seguimiento automático de descargas de archivos o vínculos de salida o los datos del tipo de conexión. Colocar la referencia de script a `s_code.js` en la etiqueta `<head>` funciona, pero el resultado es una versión muy limitada de Analytics.

El código de Analytics se puede colocar en cualquier lugar dentro de la etiqueta `<body>` de una página HTML. Adobe recomienda colocar el código de Analytics lo más cerca posible de la parte superior de la etiqueta `<body>`. Asegúrese de que todas las variables de página se establecen después de que se cargue el archivo `s_code.js`.

>[!TIP]
>
>Si desea integrar Adobe Analytics con Adobe Target, el archivo de inclusión JavaScript debe colocarse en la parte inferior de la página.
