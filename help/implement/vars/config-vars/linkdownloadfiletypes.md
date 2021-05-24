---
title: linkDownloadFileTypes
description: Determine las extensiones de archivo que se rastrean automáticamente como vínculos de descarga.
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '266'
ht-degree: 100%

---

# linkDownloadFileTypes

Cuando [`trackDownloadLinks`](trackdownloadlinks.md) se habilita y un visitante hace clic en un vínculo, AppMeasurement comprueba la dirección URL del vínculo para ver si hay extensiones de tipo de archivo. Si la dirección URL del vínculo contiene un tipo de archivo que se encuentra en `linkDownloadFileTypes`, se envía automáticamente una solicitud de imagen del vínculo de descarga.

Utilice `linkDownloadFileTypes` para personalizar las extensiones de archivo que desea contar como vínculos de descarga.

>[!NOTE]
>
>Solo se realiza un seguimiento automático de los clics reales. Los siguientes tipos de vínculos no se rastrean automáticamente:
>
> * Descargas de archivos que se inician automáticamente al cargarse una página
> * Descargas que se desencadenan tras un redireccionamiento
> * Haga clic con el botón derecho y seleccione “Guardar destino como...”
> * Vínculos que utilizan JavaScript, como `javascript:openLink()`
>
> Para estos tipos de descarga, puede llamar manualmente al método [`tl()`](../functions/tl-method.md).

Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Extensiones de descarga en Adobe Experience Platform Launch

Extensiones de descarga es una lista de extensiones de archivo con un campo para agregar más en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra el campo [!UICONTROL Extensiones de descarga].

Agregue extensiones de archivo a la lista introduciendo texto en el campo y haciendo clic en [!UICONTROL Agregar]. Elimine las extensiones de archivo de la lista haciendo clic en su icono &#39;X’ correspondiente.

## s.linkDownloadFileTypes en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkDownloadFileTypes` es una cadena de extensiones de archivo separadas por coma. No utilice espacios.

Si no se define esta variable, el seguimiento automático de vínculos de descarga no funciona (aunque [`trackDownloadLinks`](trackdownloadlinks.md) tenga el valor `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
