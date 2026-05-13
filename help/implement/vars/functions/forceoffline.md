---
title: forceOffline
description: Establezca manualmente el estado en línea de AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/TL3JVEWDI4dyW38ZFkieQJ0Fbf17WSGBLxtCmOKr7a8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 157
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
