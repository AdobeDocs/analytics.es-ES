---
title: offlineThrottleDelay
description: Establece la frecuencia de visitas cuando un dispositivo vuelve a conectarse.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 83%

---

# offlineThrottleDelay

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

Cuando un dispositivo vuelve a conectarse, todas las visitas almacenadas en el dispositivo se envían a los servidores de recopilación de datos de Adobe. Un gran número de visitas en cola puede afectar potencialmente al rendimiento en dispositivos más antiguos. Utilice la variable `offlineThrottleDelay` para establecer la frecuencia con la que las visitas en cola se envían a Adobe.

## Retraso del acelerador sin conexión mediante Web SDK

Web SDK no admite el seguimiento sin conexión.

## Retraso del acelerador sin conexión mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.offlineThrottleDelay en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.offlineThrottleDelay` es un entero que representa el número de milisegundos que AppMeasurement espera entre el envío de visitas en cola. Su valor predeterminado es `0`, que quiere decir que todas las visitas en cola se envían a la vez. Si `trackOffline` tiene el valor `false`, esta variable no hace nada.

```js
s.offlineThrottleDelay = 500;
```
