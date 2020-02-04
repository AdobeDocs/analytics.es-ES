---
title: linkDownloadFileTypes
description: Determine las extensiones de archivo que se rastrean automáticamente como vínculos de descarga.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

Cuando `trackDownloadLinks` se configura en `true` y un visitante hace clic en un vínculo, AppMeasurement comprueba la dirección URL del vínculo para ver si hay extensiones de tipo de archivo. Si la dirección URL del vínculo contiene un tipo de archivo que se encuentra en `linkDownloadFileTypes`, se envía automáticamente una solicitud de imagen del vínculo de descarga.

Utilice `linkDownloadFileTypes` para personalizar las extensiones de archivo que desea contar como vínculos de descarga.

> [!NOTE] Solo se realiza un seguimiento automático de los clics reales. Los siguientes tipos de vínculos no se rastrean automáticamente:
>
> * Descargas de archivos que se inician automáticamente cuando se carga una página
> * Descargas que se activan después de una redirección
> * Haga clic con el botón derecho y seleccione &#39;Guardar destino como...&#39;
> * Vínculos que utilizan JavaScript, como `javascript:openLink()`
>
> 
Para estos tipos de descarga, puede llamar manualmente a la `tl()` función.

Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Descargar extensiones en Adobe Experience Platform Launch

Extensiones de descarga es una lista de extensiones de archivo con un campo para agregar más en el [!UICONTROL acordeón Seguimiento] de vínculos al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el [!UICONTROL acordeón Seguimiento] de vínculos, que muestra el campo [!UICONTROL Descargar extensiones] .

Agregue extensiones de archivo a la lista introduciendo texto en el campo y haciendo clic en [!UICONTROL Agregar]. Elimine las extensiones de archivo de la lista haciendo clic en su icono X correspondiente.

## s.linkDownloadFileTypes en AppMeasurement e inicie el editor de código personalizado

La `s.linkDownloadFileTypes` variable es una cadena de extensiones de archivo separadas por coma. No utilice espacios.

Si no se define esta variable, el seguimiento automático de vínculos de descarga no funciona (aunque `trackDownloadLinks` lo sea `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
