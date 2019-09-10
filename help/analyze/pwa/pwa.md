---
title: Pwas para Analytics
seo-title: Pwas para Analytics
description: Aplicaciones web progresivas para Adobe Analytics
seo-description: Usar pwas con Analytics
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# Pwas para Analytics

En esta guía se describe cómo utilizar Adobe Analytics con aplicaciones web progresivas (PWAS).

## Primeros pasos

Pwas puede proporcionar una experiencia nativa de aplicación, así como funciones sin conexión, para un sitio web. Normalmente, pwas incluye un trabajo de servicio, disposiciones de almacenamiento en caché y un archivo de manifiesto, todos los cuales pueden ayudar con tiempos de carga más rápidos, una navegación más sencilla y un comportamiento interactivo.

Adobe Analytics funciona tan perfectamente con pwas como con sitios web tradicionales. Aunque los PWAS tienen unos cuantos requisitos para comportarse de forma progresiva y de forma progresiva, no crean barreras ni limitaciones en la forma en que Analytics recopila o informa los datos de ellos de forma diferente a los sitios Web tradicionales. De hecho, como Analytics ya incluye capacidades de seguimiento sin conexión, los PWAS pueden ayudarle a aprovechar esta característica integrada más fácilmente que con sitios web tradicionales.

## Obtención de los datos de PWA Analytics

Para recopilar y analizar los datos PWA con Analytics, no es necesario realizar cambios de configuración. Analytics proporciona automáticamente todas las funciones y funciones que utilizaría con un sitio web tradicional.

## Agregar seguimiento sin conexión para aumentar la eficacia PWA

Puede aumentar la eficacia de su PWA utilizando las capacidades de seguimiento [sin conexión de Analytics](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) . De forma predeterminada, esta función está desactivada, pero puede añadir la siguiente propiedad al archivo appmeasurement. js para activarla: `s.trackOffline=true;`.

Por ejemplo, en el siguiente archivo appmeasurement. js, la propiedad se añade al final `CONFIG SECTION`de:

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


Para obtener más información sobre la edición del archivo appmeasurement. js, consulte [Inserción de código en el archivo appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Para ver ejemplos de configuraciones en el archivo appmeasurement. js, consulte [Configuración del archivo appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7).

Para obtener más información acerca de las características del archivo appmeasurement. js, consulte la descripción general de implementación [de Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).
