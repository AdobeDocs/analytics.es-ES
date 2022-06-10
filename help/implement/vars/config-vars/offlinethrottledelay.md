---
title: offlineThrottleDelay
description: Establece la frecuencia de visitas cuando un dispositivo vuelve a conectarse.
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 81%

---

# offlineThrottleDelay

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

Cuando un dispositivo vuelve a conectarse, todas las visitas almacenadas en el dispositivo se envían a los servidores de recopilación de datos de Adobe. Un gran número de visitas en cola puede afectar potencialmente al rendimiento en dispositivos más antiguos. Utilice la variable `offlineThrottleDelay` para establecer la frecuencia con la que las visitas en cola se envían a Adobe.

## Retraso de aceleración sin conexión con la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.offlineThrottleDelay en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.offlineThrottleDelay` es un entero que representa el número de milisegundos que AppMeasurement espera entre el envío de visitas en cola. Su valor predeterminado es `0`, que quiere decir que todas las visitas en cola se envían a la vez. Si `trackOffline` tiene el valor `false`, esta variable no hace nada.

```js
s.offlineThrottleDelay = 500;
```
