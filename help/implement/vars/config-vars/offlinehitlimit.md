---
title: offlineHitLimit
description: Determinar el número máximo de visitas en cola para el seguimiento sin conexión.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/YaAPaPRLQ7YYxARVRBuxB1J25qeS8JTPbIO1Bj725YM'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 39%

---

# offlineHitLimit

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La variable `offlineHitLimit` coloca un límite en el número de visitas que almacena el dispositivo localmente. Esta variable solo funciona si [`trackOffline`](trackoffline.md) está habilitada.

## Límite de visitas sin conexión mediante Web SDK

Web SDK no admite el seguimiento sin conexión.

## Límite de visitas sin conexión mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.offlineHitLimit en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.offlineHitLimit` es un número entero que representa el número máximo de visitas que un dispositivo almacena mientras están sin conexión. Si no se define esta variable, el valor predeterminado es `10`. Puede establecerlo en cualquier valor entero. Cuando establezca valores altos, tenga en cuenta los límites de almacenamiento local en el explorador de un visitante. Este límite suele ser de 5 a 10 MB.

```js
s.offlineHitLimit = 100;
```
