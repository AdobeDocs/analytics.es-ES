---
title: linkDownloadFileTypes
description: Determine las extensiones de archivo que se rastrean automáticamente como vínculos de descarga.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 55%

---

# linkDownloadFileTypes

Cuándo [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (SDK web) está habilitado y un visitante hace clic en un vínculo, AppMeasurement comprueba la URL del vínculo para ver si hay extensiones de tipo de archivo. Si la dirección URL del vínculo contiene un tipo de archivo coincidente, se envía automáticamente una solicitud de imagen del vínculo de descarga.

Utilice `linkDownloadFileTypes` para personalizar las extensiones de archivo que desea contar como vínculos de descarga.

>[!NOTE]
>
>Solo se realiza un seguimiento automático de los clics reales. Los siguientes tipos de vínculos no se rastrean automáticamente:
>
>* Descargas de archivos que se inician automáticamente al cargarse una página
>* Descargas que se desencadenan tras un redireccionamiento
>* Haga clic con el botón derecho y seleccione “Guardar destino como...”
>* Vínculos que utilizan JavaScript, como `javascript:openLink()`
>
>Para estos tipos de descarga, puede enviar manualmente una [`link tracking`](../functions/tl-method.md) llamada.

Si un vínculo en el que se hizo clic coincide con los criterios de vínculo de salida y de descarga, el tipo de vínculo de descarga tiene prioridad.

## Descargar calificador de vínculo con la extensión SDK para web

El [!UICONTROL Descargar calificador de vínculo] El campo de texto utiliza la expresión regular para determinar si un vínculo en el que se hizo clic cumple los requisitos para ser un vínculo de descarga.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Recopilación de datos], establezca el valor deseado en **[!UICONTROL Descargar calificador de vínculo]** campo de texto.

## Descargar calificador de vínculos manualmente implementando el SDK web

[Configurar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) el SDK mediante [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es#automaticLinkTracking). El campo utiliza la expresión regular de la dirección URL donde se hizo clic para determinar si es un vínculo de descarga válido. If `downloadLinkQualifier` no está definida, el valor predeterminado se establece en `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Extensiones de descarga con la extensión Adobe Analytics

Extensiones de descarga es una lista de extensiones de archivo con un campo para agregar más en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra el campo **[!UICONTROL Extensiones de descarga]**.

Agregue extensiones de archivo a la lista introduciendo texto en el campo y haciendo clic en **[!UICONTROL Agregar]**. Elimine las extensiones de archivo de la lista haciendo clic en sus respectivas **&#39;X&#39;** icono.

## s.linkDownloadFileTypes en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkDownloadFileTypes` es una cadena de extensiones de archivo separadas por coma. No utilice espacios.

Si no se define esta variable, el seguimiento automático de vínculos de descarga no funciona (aunque [`trackDownloadLinks`](trackdownloadlinks.md) tenga el valor `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
