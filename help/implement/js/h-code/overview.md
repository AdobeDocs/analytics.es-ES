---
title: Introducción a la implementación de código H JavaScript
description: Conozca el flujo de trabajo para implementar el código H en su sitio.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Introducción a la implementación de código H JavaScript

> [!IMPORTANT] Esta versión de recopilación de datos ya no es compatible. Actualice a [Adobe Experience Platform Launch](../../launch/overview.md) o [AppMeasurement para JavaScript](../overview.md).

Debe tener acceso a los servidores de alojamiento para implementar correctamente una página con código para recopilar datos. Los pasos siguientes le guían a través de una implementación básica de Analytics H Code.

> [!NOTE] Para seguir estas instrucciones, ya debe tener una copia existente de `s_code.js` . Adobe ya no ofrece la opción de descargar el código H en el Administrador de códigos.

1. **Actualizar variables** de archivo JS principales: Edite el `s_code.js` archivo y asegúrese de actualizar las siguientes variables:
   * `s_account` contiene la ID del grupo de informes al que desea enviar los datos. Consulte
   * `s.trackingServer` contiene la ubicación en la que se almacenan las cookies. Consulte [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Aloje el`s_code.js`archivo en el sitio**: Este archivo suele residir con otras secuencias de comandos del servidor web.
3. **Referencia`s_code.js`en todas las páginas**: Asegúrese de que todas las páginas individuales llamen al archivo principal de JavaScript y hágalo dentro de la `<body>` etiqueta HTML (no la `<head>` etiqueta).
   > [!TIP] El código H requiere que se llame a la `s_code.js` secuencia de comandos dentro de la `<body>` etiqueta . Esto es diferente a otros métodos de implementación, la mayoría de los cuales requieren que las referencias de secuencia de comandos estén en la `<head>` etiqueta .
4. **Defina las variables específicas de la página en cada página**: Cada página debe tener variables individuales definidas, como el nombre de la página o las eVars. Las variables individuales generalmente se definen con una `<script>` etiqueta en línea en cada página.
5. **Use el depurador para verificar la recopilación** de datos: Descargue e instale el depurador [de](../../validate/debugger.md) Experience Cloud para asegurarse de que los datos se envían a Adobe y de que las variables de página se definen correctamente.

## Almacenamiento en caché

El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general.

## Compresión de código H

Si le preocupa el tamaño de descarga del `s_code.js` archivo, Adobe recomienda comprimir el `s_code.js` archivo con GZIP. GZIP es compatible con todos los exploradores principales y ofrece un mejor rendimiento que la compresión JavaScript. Consulte Módulo [Apache mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) en la documentación de Apache.
