---
title: useBeacon
description: useBeacon le permite forzar AppMeasurement para que utilice la API sendBeacon de los navegadores
keywords: Analytics Implementation
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

La variable `s.useBeacon` fuerza a la siguiente solicitud a utilizar la [API sendBeacon](https://developer.mozilla.org/es-ES/docs/Web/API/Navigator/sendBeacon) del explorador. El uso de `s.sendBeacon` permite enviar una solicitud HTTP fuera del contexto de una página. Resulta útil para los vínculos de salida y otras situaciones en las que desea enviar información antes de que se descargue la página.

La configuración de este valor solo se aplica a la siguiente solicitud que activa AppMeasurement. Cuando se activa la solicitud, `s.useBeacon` se restablece en “false”. Esta variable se aplica tanto a solicitudes `s.t()` como a solicitudes de imagen `s.tl()`.

El uso de la variable `s.useBeacon` requiere AppMeasurement 2.17.0 o superior.

> [!NOTE] [Vínculos de salida](s-linktrackvars.md) utiliza esta variable automáticamente sin necesidad de ninguna configuración.

## Sintaxis

```js
s.useBeacon = true;
```
