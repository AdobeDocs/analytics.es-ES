---
title: forceOffline
description: Establezca manualmente el estado en línea de AppMeasurement.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

---

# forceOffline

El método `forceOffline()` permite anular el estado detectado automáticamente de AppMeasurement.

>[!IMPORTANT]
>
>Utilice esta función únicamente cuando [`trackOffline`](../config-vars/trackoffline.md) esté habilitada. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el método `forceOffline()` para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera sin conexión. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzado de la desconexión mediante etiquetas en Adobe Experience Platform

No hay ningún campo específico en la IU de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.forceOffline() en el editor de código personalizado de AppMeasurement y 

Puede llamar al método `s.forceOffline()` desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOffline();
```
