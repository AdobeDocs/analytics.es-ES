---
title: linkDownloadFileTypes
description: Determine las extensiones de archivo que se rastrean automáticamente como vínculos de descarga.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkDownloadFileTypes

Cuando [`trackDownloadLinks`](trackdownloadlinks.md) está habilitado y un visitante hace clic en un vínculo, AppMeasurement comprueba la dirección URL del vínculo en busca de extensiones de tipo de archivo. Si la dirección URL del vínculo contiene un tipo de archivo que se encuentra en `linkDownloadFileTypes`, se envía automáticamente una solicitud de imagen del vínculo de descarga.

Utilice `linkDownloadFileTypes` para personalizar las extensiones de archivo que desea contar como vínculos de descarga.

> [!NOTE] Solo se realiza un seguimiento automático de los clics reales. Los siguientes tipos de vínculos no se rastrean automáticamente:
>
> * Descargas de archivos que se inician automáticamente cuando se carga una página
> * Descargas que se activan después de una redirección
> * Haga clic con el botón derecho y seleccione &#39;Guardar destino como...&#39;
> * Vínculos que utilizan JavaScript, como `javascript:openLink()`
>
> 
Para estos tipos de descarga, puede llamar manualmente al [`tl()`](../functions/tl-method.md) método.

Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Descargar extensiones en Adobe Experience Platform Launch

Extensiones de descarga es una lista de extensiones de archivo con un campo para agregar más bajo el [!UICONTROL Link Tracking] acordeón al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de Adobe Analytics.
4. Expanda el [!UICONTROL Link Tracking] acordeón, que muestra el [!UICONTROL Download Extensions] campo.

Agregue extensiones de archivo a la lista introduciendo texto en el campo y haciendo clic en [!UICONTROL Add]. Elimine las extensiones de archivo de la lista haciendo clic en el icono &#39;X&#39; correspondiente.

## s.linkDownloadFileTypes en AppMeasurement e inicie el editor de código personalizado

La `s.linkDownloadFileTypes` variable es una cadena de extensiones de archivo separadas por coma. No utilice espacios.

Si no se define esta variable, el seguimiento automático de vínculos de descarga no funciona (aunque [`trackDownloadLinks`](trackdownloadlinks.md) lo sea `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
