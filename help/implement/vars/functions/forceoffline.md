---
title: forceOffline
description: Establezca manualmente el estado en línea de AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOffline

El método `forceOffline()` permite anular el estado detectado automáticamente de AppMeasurement.

>[!WARNING]
>
>Utilice esta función únicamente cuando [`trackOffline`](../config-vars/trackoffline.md) esté habilitada. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el método `forceOffline()` para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera sin conexión. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzar desconexión mediante Web SDK

Web SDK no admite el seguimiento sin conexión.

## Forzado de la desconexión mediante la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.forceOffline() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Puede llamar al método `s.forceOffline()` desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOffline();
```
