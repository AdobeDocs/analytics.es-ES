---
title: forceOnline
description: Establezca manualmente el estado en línea de AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

El `forceOnline()` método permite anular el estado detectado automáticamente de AppMeasurement.

> [!IMPORTANT] Utilice este método únicamente cuando [`trackOffline`](../config-vars/trackoffline.md) esté habilitado. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el `forceOnline()` método para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera en línea. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzar en línea en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.forceOnline() en AppMeasurement e inicie el editor de código personalizado

Puede llamar al `s.forceOnline()` método desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOnline();
```
