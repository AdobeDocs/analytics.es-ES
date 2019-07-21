---
description: Es responsabilidad del cliente probar las modificaciones del archivo .JS o del código HTML. Las pruebas deben realizarse antes de publicar las modificaciones en los sitios web de producción.
keywords: Implementación de Analytics
seo-description: Es responsabilidad del cliente probar las modificaciones del archivo .JS o del código HTML. Las pruebas deben realizarse antes de publicar las modificaciones en los sitios web de producción.
seo-title: Modificaciones del código
solution: Analytics
title: Modificaciones del código
topic: Desarrollador e implementación
uuid: efac 045 e -15 f 5-45 f 6-a 21 a-de 6 c 4 b 0 a 8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modificaciones del código

Es responsabilidad del cliente probar las modificaciones del archivo .JS o del código HTML. Las pruebas deben realizarse antes de publicar las modificaciones en los sitios web de producción.

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. Asegúrese de que JavaScript se ejecuta sin errores en todas las páginas y plantillas de página (en Internet Explorer, en Opciones de Internet, seleccione la pestaña Opciones avanzadas, haga clic en Mostrar una notificación sobre cada error de script.

Cuando realice las pruebas de errores, pegue el código en una página HTML predeterminada para determinar si el error lo están produciendo otros elementos u objetos de la página.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

