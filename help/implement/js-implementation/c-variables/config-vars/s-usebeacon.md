---
title: useBeacon
description: useBeacon le permite forzar AppMeasurement para que utilice la API sendBeacon de los navegadores
keywords: Analytics Implementation
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.useBeacon

La `s.useBeacon` variable fuerza a la siguiente solicitud a utilizar la API [](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)sendBeacon del explorador. El uso `s.sendBeacon` permite enviar una solicitud HTTP fuera del contexto de una página. Resulta útil para los vínculos de salida y otras situaciones en las que desea enviar información antes de que se descargue la página.

La configuración de este valor solo se aplica a la siguiente solicitud que activa AppMeasurement. Cuando se activa la solicitud, `s.useBeacon` se restablece en false. Esta variable se aplica tanto a solicitudes `s.t()` como a solicitudes de `s.tl()` imagen.

El uso de la `s.useBeacon` variable requiere AppMeasurement 2.17.0 o superior.

> [!NOTE] [ExitLinks](s-linktrackvars.md) utiliza esta variable automáticamente sin ninguna configuración adicional.

## Sintaxis

```js
s.useBeacon = true;
```
