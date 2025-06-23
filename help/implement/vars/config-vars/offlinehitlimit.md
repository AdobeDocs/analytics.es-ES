---
title: offlineHitLimit
description: Determinar el número máximo de visitas en cola para el seguimiento sin conexión.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '193'
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
