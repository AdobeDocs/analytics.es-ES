---
title: useBeacon
description: useBeacon le permite forzar AppMeasurement para que utilice la API sendBeacon de los navegadores
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# useBeacon

La mayoría de los exploradores modernos incluyen el método nativo `navigator.sendBeacon()`. Envía asincrónicamente una pequeña cantidad de datos a través de HTTP a un servidor web. AppMeasurement puede utilizar el `navigator.sendBeacon()` método si la `useBeacon` variable está habilitada. Resulta útil para los vínculos de salida y otras situaciones en las que desea enviar información antes de que se descargue la página.

Si `useBeacon` está activada, la siguiente visita enviada a Adobe utiliza el `navigator.sendBeacon()` método del explorador en lugar de una solicitud de `GET` imagen estándar. Esta variable se aplica tanto a solicitudes [`s.t()`](../functions/t-method.md) como a solicitudes de imagen [`s.tl()`](../functions/tl-method.md). Requiere AppMeasurement 2.17.0 o superior.

> [!TIP] AppMeasurement habilita automáticamente `useBeacon` las solicitudes de imagen de vínculo de salida.

La `useBeacon` variable se omite cuando el visitante utiliza un explorador que no admite `navigator.sendBeacon()`. El uso de esta variable requiere AppMeasurement 2.16.0 o superior.

## Usar señalización en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.useBeacon en el editor de código personalizado AppMeasurement e Launch

La `s.useBeacon` variable es un booleano que determina si AppMeasurement utiliza el `navigator.sendBeacon()` método del explorador. Its default value is `false`. Establezca esta variable en `true` antes de llamar a una función de seguimiento si desea utilizar la naturaleza asincrónica de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

> [!NOTE] Después de ejecutar una llamada de seguimiento, esta variable se restablece a `false`. Si la implementación envía varias solicitudes de imagen en la misma carga de página (como aplicaciones de una sola página), establezca esta variable en antes de `true` cada llamada de seguimiento.
