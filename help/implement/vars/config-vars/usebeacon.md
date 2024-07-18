---
title: useBeacon
description: useBeacon le permite forzar AppMeasurement para que utilice la API sendBeacon de los navegadores
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 62%

---

# useBeacon

La mayoría de los exploradores modernos incluyen el método nativo `navigator.sendBeacon()`. Envía asincrónicamente una pequeña cantidad de datos a través de HTTP a un servidor web. AppMeasurement puede utilizar el método `navigator.sendBeacon()` si la variable `useBeacon` está habilitada. Resulta útil para los vínculos de salida y otras situaciones en las que desea enviar información antes de que se descargue la página.

Si `useBeacon` está activada, la siguiente visita enviada a Adobe utiliza el método del explorador `navigator.sendBeacon()` en lugar de una solicitud de imagen estándar `GET`. Esta variable se aplica tanto a solicitudes [`s.t()`](../functions/t-method.md) como a solicitudes de imagen [`s.tl()`](../functions/tl-method.md). Requiere AppMeasurement 2.17.0 o superior.

>[!TIP]
>
>AppMeasurement habilita automáticamente `useBeacon` para las solicitudes de imagen de vínculo de salida.

La variable `useBeacon` se omite cuando el visitante utiliza un explorador que no admite `navigator.sendBeacon()`. El uso de esta variable requiere AppMeasurement 2.16.0 o superior.

## Utilice la API sendBeacon con la extensión del SDK web

La casilla de verificación **[!UICONTROL Documento descargará]** dentro de una Configuración de acción determina si los datos enviados al Adobe utilizan la API sendBeacon.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee.
1. En [!UICONTROL Acciones], haga clic en la acción que desee o en el icono **&#39;+&#39;** para agregar una acción nueva.
1. Establece la lista desplegable [!UICONTROL Extension] en **[!UICONTROL SDK web de Adobe Experience Platform]** y el [!UICONTROL tipo de acción] en **[!UICONTROL Enviar evento]**
1. Haga clic en la casilla de verificación **[!UICONTROL El documento se descargará]** a la derecha.

Si se marca esta casilla, los datos se envían al Adobe mediante la API sendBeacon. De forma predeterminada, está desactivada.

## Utilice la API sendBeacon para implementar manualmente el SDK web

Establezca `documentUnloading` en `true` al enviar un evento. Si no se establece, su valor predeterminado es `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Consulte [Uso de la API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) en la documentación del SDK web para obtener más información.

## Uso de la señalización mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.useBeacon en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.useBeacon` es un booleano que determina si AppMeasurement utiliza el método `navigator.sendBeacon()` del explorador. Su valor predeterminado es `false`. Establezca esta variable como `true` antes de llamar a una función de seguimiento si desea utilizar la naturaleza asincrónica de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Después de ejecutar una llamada de seguimiento, esta variable se restablece a `false`. Si la implementación envía varias solicitudes de imagen en la misma carga de página (como aplicaciones de una sola página), establezca esta variable como `true` antes de cada llamada de seguimiento.
