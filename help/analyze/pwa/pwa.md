---
title: PWA para Analytics
description: Aplicaciones web progresivas para Adobe Analytics
role: Business Practitioner, Administrator
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
translation-type: tm+mt
source-git-commit: 960274fde798287568ada9e6d8ec96783449dd99
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 88%

---

# PWA para Adobe Analytics

En esta página, se describe cómo utilizar Adobe Analytics con aplicaciones web progresivas (PWA).

## Primeros pasos

Los archivos PWA pueden proporcionar a un sitio web una experiencia nativa de la aplicación y funciones sin conexión. Normalmente, los archivos PWA incluyen un trabajo de servicio, provisiones en caché y un archivo de manifiesto. Todo ello permite agilizar los tiempos de carga, facilita la navegación y mejora el comportamiento interactivo.

Adobe Analytics funciona igual de bien con los PWA que con los sitios web tradicionales. Los PWA tienen algunos requisitos adicionales para comportarse de forma progresiva en sí mismos. Pese a ello, no crean barreras ni limitaciones diferentes a las de los sitios web tradicionales en lo relativo a cómo Analytics recopila sus datos o realiza informes de los mismos. De hecho, dado que Analytics ya incluye funciones de seguimiento sin conexión, los PWA pueden ayudarle a aprovechar esta función integrada con más facilidad que con los sitios web tradicionales.

## Obtenga sus datos de PWA de Analytics

Para recopilar y analizar los datos de los PWA de [!UICONTROL Analytics], no es necesario realizar ningún cambio en la configuración. [!UICONTROL Analytics] proporciona automáticamente las mismas funciones y características que tendría en un sitio web tradicional.

## Agregar un seguimiento sin conexión para aumentar la eficacia de los PWA

Puede aumentar la eficacia de su PWA mediante el uso de las [funcionalidades de seguimiento sin conexión](/help/implement/vars/config-vars/trackoffline.md) de Adobe Analytics. De forma predeterminada, esta función está desactivada, pero puede agregar la siguiente propiedad al archivo AppMeasurement.js para activarla: `s.trackOffline=true;`.

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

Para obtener más información sobre la edición del archivo AppMeasurement.js, consulte [Insertar código principal de AppMeasurement](/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md).

Para obtener más información sobre la configuración del archivo AppMeasurement.js, consulte [Información general sobre las variables de configuración](/help/implement/vars/config-vars/configuration-variables.md) y las páginas específicas de las variables individuales en el mismo subcapítulo.

Para obtener más información sobre las características del archivo AppMeasurement.js, consulte la [Descripción general de la implementación de Javascript](/help/implement/js/overview.md).
