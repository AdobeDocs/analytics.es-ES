---
title: offlineHitLimit
description: Determinar el número máximo de visitas en cola para el seguimiento sin conexión.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La `offlineHitLimit` variable coloca un límite en el número de visitas que almacena localmente el dispositivo. Esta variable solo funciona si [`trackOffline`](trackoffline.md) está habilitada.

## Límite de visitas sin conexión en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.offlineHitLimit en AppMeasurement e inicie el editor de código personalizado

La `s.offlineHitLimit` variable es un entero que representa el número máximo de visitas que un dispositivo almacena mientras están sin conexión. Si no se define esta variable, no hay límite en el número de visitas que almacena un dispositivo mientras está sin conexión.

```js
s.offlineHitLimit = 100;
```
