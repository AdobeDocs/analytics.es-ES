---
title: offlineHitLimit
description: Determinar el número máximo de visitas en cola para el seguimiento sin conexión.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 79%

---

# offlineHitLimit

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La variable `offlineHitLimit` coloca un límite en el número de visitas que almacena el dispositivo localmente. Esta variable solo funciona si [`trackOffline`](trackoffline.md) está habilitada.

## Límite de visitas sin conexión mediante la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.offlineHitLimit en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.offlineHitLimit` es un número entero que representa el número máximo de visitas que un dispositivo almacena mientras están sin conexión. Si no se define esta variable, no hay límite en el número de visitas que almacena un dispositivo mientras está sin conexión.

```js
s.offlineHitLimit = 100;
```
