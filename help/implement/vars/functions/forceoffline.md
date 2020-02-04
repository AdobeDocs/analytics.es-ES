---
title: forceOffline
description: Establezca manualmente el estado en línea de AppMeasurement.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOffline

El `forceOffline` método permite anular el estado detectado automáticamente de AppMeasurement.

> [!IMPORTANT] Utilice esta función únicamente cuando `trackOffline` esté habilitada. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el `forceOffline` método para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera sin conexión. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzar desconexión en el lanzamiento de Adobe Experience Platform

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.forceOffline() en el editor de código personalizado de AppMeasurement e Launch

Puede llamar al `s.forceOffline()` método desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOffline();
```
