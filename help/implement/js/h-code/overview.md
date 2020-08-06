---
title: Introducción a la implementación de código H de JavaScript
description: Conozca el flujo de trabajo para implementar el código H en su sitio.
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---


# Introducción a la implementación de código H de JavaScript

>[!IMPORTANT]
>
>Esta versión de recopilación de datos ya no es compatible. Utilice [Adobe Experience Platform Launch](../../launch/overview.md) o [AppMeasurement para JavaScript](../overview.md).

Debe tener acceso a los servidores de alojamiento para implementar correctamente una página con código para recopilar datos. A continuación se muestran los pasos de una implementación básica código H de Analytics.

>[!NOTE]
>
> Para seguir estas instrucciones, ya debe tener una copia de `s_code.js`. Adobe ya no ofrece la opción de descargar el código H en el Administrador de códigos.

1. **Actualizar variables de archivos JS principales**: Edite el archivo `s_code.js` y asegúrese que las siguientes variables están actualizadas:
   * `s_account` contiene el ID del grupo de informes al que desea enviar los datos. Consulte
   * `s.trackingServer` contiene la ubicación en la que se almacenan las cookies. Consulte [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Aloje el archivo`s_code.js`en el sitio**: Este archivo suele alojarse con otras secuencias de comandos del servidor web.
1. **Haga referencia a`s_code.js`en todas las páginas**: Asegúrese de que todas las páginas individuales llamen al archivo principal de JavaScript y hágalo dentro de la etiqueta HTML `<body>` (no la etiqueta `<head>`).

   >[!TIP]
   >
   > El código H requiere que se llame al script `s_code.js` dentro de la etiqueta `<body>`. Esto es diferente a otros métodos de implementación, la mayoría de los cuales requieren que las referencias de secuencia de comandos estén en la etiqueta `<head>`.
1. **Defina las variables específicas de la página en cada página**: Cada página debe tener variables individuales definidas, como el nombre de la página o las eVars. Las variables individuales generalmente se definen con una etiqueta `<script>` en línea en cada página.
1. **Use Debugger para verificar la recopilación de datos**: Descargue e instale [Experience Cloud Debugger](../../validate/debugger.md) para asegurarse de que los datos se envían a Adobe y de que las variables de página se definen correctamente.

## Almacenamiento en caché

El archivo JavaScript se almacena en caché en el explorador del visitante cuando se carga por primera vez y, por lo general, solo se descarga una vez por sesión. El archivo no se descarga en cada página, aunque lo usen todas las páginas del sitio. El cálculo promedio indica que, en la mayoría de sitios web, se registran varias vistas de página por sesión por usuario. De este modo, si se transfieren a este archivo los elementos JavaScript que se usan varias veces, se pueden reducir los datos que se descargan de forma general.

## Compresión de código H

Si le preocupa el tamaño de descarga del archivo `s_code.js`, Adobe recomienda comprimir el archivo `s_code.js` con GZIP. GZIP es compatible con todos los exploradores principales y ofrece un mejor rendimiento que la compresión JavaScript. Consulte el [Módulo Apache mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) en la documentación de Apache.
