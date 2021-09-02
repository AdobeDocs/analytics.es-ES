---
title: forceOnline
description: Establezca manualmente el estado en línea de AppMeasurement.
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

---

# forceOnline

El método `forceOnline()` permite anular el estado detectado automáticamente de AppMeasurement.

>[!IMPORTANT]
>
>Utilice este método únicamente cuando [`trackOffline`](../config-vars/trackoffline.md) esté habilitada. El uso de esta función fuera del seguimiento sin conexión puede causar la pérdida de datos.

AppMeasurement detecta automáticamente el estado en línea del dispositivo. Puede utilizar el método `forceOnline()` para obligar a AppMeasurement a tratar las visitas como si el dispositivo estuviera en línea. Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es sobrescribir el estado en línea en AppMeasurement.

## Forzado de la conexión mediante etiquetas en Adobe Experience Platform

No hay ningún campo específico en la IU de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.forceOnline() en el editor de código personalizado de AppMeasurement y 

Puede llamar al método `s.forceOnline()` desde cualquier lugar de la implementación después de crear una instancia del objeto de Analytics.

```js
s.forceOnline();
```
