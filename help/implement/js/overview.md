---
title: AppMeasurement para JavaScript
description: Obtenga información sobre cómo implementar Adobe Analytics mediante JavaScript sin un sistema de administración de etiquetas.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 100%

---


# AppMeasurement para JavaScript

Históricamente, AppMeasurement para JavaScript ha sido un método común para implementar Adobe Analytics. Sin embargo, con la creciente popularidad de los sistemas de Tag Management, se recomienda utilizar [Adobe Experience Platform Launch](../launch/overview.md).

## Flujo de trabajo general que envía datos a Adobe mediante JavaScript

1. Cargue el archivo de `AppMeasurement.js`. Este archivo contiene las bibliotecas necesarias para enviar datos a Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Defina las variables de configuración de `AppMeasurement.js`. Cuando se crea una instancia del objeto de Analytics, estas variables garantizan que la configuración de recopilación de datos sea correcta. Consulte [Variables de configuración](../vars/config-vars/configuration-variables.md) para obtener una lista completa de las variables que puede definir.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Defina las variables de nivel de página dentro del código de página del sitio. Estas variables determinan la dimensión y las métricas específicas que se envían a Adobe. Consulte [Variables de página](../vars/page-vars/page-variables.md) para obtener una lista completa de las variables que puede definir.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Cuando se definan todos los métodos de nivel de página, envíe los datos a Adobe mediante la función `t()`. Consulte [t](../vars/functions/t-method.md) para obtener más información.

   ```js
   s.t();
   ```
