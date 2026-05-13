---
title: Solución de problemas de implementaciones de código H
description: Descubra algunos problemas comunes con las implementaciones de JavaScript heredadas.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 100%

---

# Solución de problemas de implementaciones de código H

A continuación se indican los pasos para la resolución de problemas específicos de las implementaciones de código H.

## Incluir código de Analytics en la etiqueta Head

>[!NOTE]
>
>Aunque las implementaciones de código H requieren que se haga referencia al código en la etiqueta `<body>`, otras implementaciones (como el uso de etiquetas en Adobe Experience Platform) requieren que se haga referencia al código en la etiqueta `<head>`.

El código de Analytics crea una imagen de 1x1 píxeles invisible. Anteriormente, una práctica común de implementación era colocar la referencia a `s_code.js` en la etiqueta `<head>`. Colocar el código aquí evitaba que la imagen afectara al diseño de la página de alguna manera. Esto se ejecuta antes, lo que optimiza el recuento de las vistas de página para cargas de página parciales.

Sin embargo, algunos elementos del código requieren que el objeto `<body>` esté presente. Si el código JavaScript de Analytics está en la etiqueta `<head>`, se ejecuta antes de que exista el objeto `<body>`. Como resultado, la implementación no recopila datos de [!UICONTROL ClickMap] y el seguimiento automático de descargas de archivos o vínculos de salida o los datos del tipo de conexión. Colocar la referencia de script a `s_code.js` en la etiqueta `<head>` funciona, pero el resultado es una versión muy limitada de Analytics.

El código de Analytics se puede colocar en cualquier lugar dentro de la etiqueta `<body>` de una página HTML. Adobe recomienda colocar el código de Analytics lo más cerca posible de la parte superior de la etiqueta `<body>`. Asegúrese de que todas las variables de página se establecen después de que se cargue el archivo `s_code.js`.

>[!TIP]
>
>Si desea integrar Adobe Analytics con Adobe Target, el archivo de inclusión JavaScript debe colocarse en la parte inferior de la página.
