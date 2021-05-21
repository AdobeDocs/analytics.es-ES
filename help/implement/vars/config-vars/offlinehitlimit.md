---
title: offlineHitLimit
description: Determinar el número máximo de visitas en cola para el seguimiento sin conexión.
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---

# offlineHitLimit

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La variable `offlineHitLimit` coloca un límite en el número de visitas que almacena el dispositivo localmente. Esta variable solo funciona si [`trackOffline`](trackoffline.md) está habilitada.

## Límite de visitas sin conexión en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.offlineHitLimit en el editor de código personalizado de AppMeasurement y Launch

La variable `s.offlineHitLimit` es un número entero que representa el número máximo de visitas que un dispositivo almacena mientras están sin conexión. Si no se define esta variable, no hay límite en el número de visitas que almacena un dispositivo mientras está sin conexión.

```js
s.offlineHitLimit = 100;
```
