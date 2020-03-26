---
title: PWA para Analytics
description: Aplicaciones web progresivas para Adobe Analytics
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# PWA para Analytics

En esta página se describe cómo utilizar Adobe Analytics con aplicaciones web progresivas (PWA).

## Primeros pasos

Los archivos PWA pueden proporcionar una experiencia nativa de la aplicación, así como funciones sin conexión, para un sitio web. Normalmente, los archivos PWA incluyen un trabajador de servicios, provisiones en caché y un archivo de manifiesto, todo lo cual puede ayudar a agilizar los tiempos de carga, facilitar la navegación y mejorar el comportamiento interactivo.

Adobe Analytics funciona igual de bien con los PWA que con los sitios web tradicionales. Aunque los PWA tienen algunos requisitos más para comportarse de forma progresiva en sí mismos, no crean barreras ni limitaciones a la forma en que Analytics recopila o informa datos de ellos de forma diferente a los sitios web tradicionales. De hecho, como Analytics ya incluye funciones de seguimiento sin conexión, los PWA pueden ayudarle a aprovechar esta función integrada con más facilidad que con los sitios web tradicionales.

## Obtener los datos de análisis de PWA

Para recopilar y analizar los datos de PWA con Analytics, no es necesario realizar ningún cambio en la configuración. Analytics proporciona automáticamente las mismas funciones y características que con un sitio web tradicional.

## Añadir el seguimiento sin conexión para aumentar la eficacia de PWA

Puede aumentar la eficacia de su PWA mediante el uso de las capacidades [de seguimiento](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) sin conexión de Analytics. De forma predeterminada, esta función está desactivada, pero puede agregar la siguiente propiedad al archivo AppMeasurement.js para activarla: `s.trackOffline=true;`.

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

Para obtener más información sobre la edición del archivo AppMeasurement.js, consulte [Inserción de código en el archivo AppMeasurement.js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Para obtener ejemplos de configuraciones en el archivo AppMeasurement.js, consulte [Configuración del archivo](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)AppMeasurement.js.

Para obtener más información sobre las características del archivo AppMeasurement.js, consulte la descripción general [de la implementación de](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)Javascript.
