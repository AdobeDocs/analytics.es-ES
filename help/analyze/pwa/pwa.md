---
title: PWA para Analytics
description: Aplicaciones web progresivas para Adobe Analytics
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 75%

---


# PWAs para Adobe Analytics

En esta página se describe cómo utilizar Adobe Analytics con aplicaciones web progresivas (PWA).

## Primeros pasos

Los archivos PWA pueden proporcionar a un sitio web una experiencia nativa de la aplicación y funciones sin conexión. Normalmente, los archivos PWA incluyen un trabajo de servicio, provisiones en caché y un archivo de manifiesto. Todo ello permite agilizar los tiempos de carga, facilita la navegación y mejora el comportamiento interactivo.

Adobe Analytics funciona igual de bien con los PWA que con los sitios web tradicionales. Los PWA tienen algunos requisitos adicionales para comportarse de forma progresiva en sí mismos. Pese a ello, no crean barreras ni limitaciones diferentes a las de los sitios web tradicionales en lo relativo a cómo Analytics recopila sus datos o realiza informes de los mismos. De hecho, como Analytics ya incluye funciones de seguimiento sin conexión, los PWA pueden ayudarle a aprovechar esta función integrada con más facilidad que con los sitios web tradicionales.

## Obtener los datos de análisis de PWA

To collect and analyze your PWA data with [!UICONTROL Analytics], you do not need to  make any configuration changes. [!UICONTROL Analytics proporciona automáticamente las mismas funciones y características que tendría en un sitio web tradicional.]

## Agregar un seguimiento sin conexión para aumentar la eficacia de los PWA

You can increase the effectiveness of your PWA by using Adobe Analytics [offline tracking capabilities](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/functions/forceoffline.translate.html) with it. De forma predeterminada, esta función está desactivada, pero puede agregar la siguiente propiedad al archivo AppMeasurement.js para activarla: `s.trackOffline=true;`.

Por ejemplo, en el siguiente archivo AppMeasurement.js, la propiedad se agrega al final del `CONFIG SECTION`:

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
*** 
```

Para obtener más información sobre la edición del archivo AppMeasurement.js, consulte [Inserción de código en el archivo AppMeasurement.js](https://docs.adobe.com/content/help/es-ES/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

Para obtener ejemplos de configuraciones en el archivo AppMeasurement.js, consulte [Configuración del archivo AppMeasurement.js](https://docs.adobe.com/content/help/es-ES/analytics/implementation/js/overview.translate.html#section_042412C29CC249E298F19B2BC2F43CE7).

Para obtener más información sobre las características del archivo AppMeasurement.js, consulte la [descripción general de la implementación de Javascript](https://docs.adobe.com/content/help/es-ES/analytics/implementation/js/migrate-from-hcode.translate.html).
