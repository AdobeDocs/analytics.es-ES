---
title: forceOnline
description: Establezca manualmente el estado en línea de AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/qPSlGDmNTccOtGRvlu-xr-wf1hV18OA-yyiuScnZr7g'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 157
ht-degree: 80%

---

# forceOnline

El método `forceOnline()` permite anular el estado detectado automáticamente de AppMeasurement.

>[!WARNING]
>
>Utilice este método únicamente cuando [`trackOffline`](../config-vars/trackoffline.md) esté habilitada. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el método `forceOnline()` para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera en línea. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzado de la conexión mediante Web SDK

Web SDK no admite el seguimiento sin conexión.

## Forzado de la conexión con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.forceOnline() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Puede llamar al método `s.forceOnline()` desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOnline();
```
