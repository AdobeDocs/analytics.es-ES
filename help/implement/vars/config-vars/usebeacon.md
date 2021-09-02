---
title: useBeacon
description: useBeacon le permite forzar AppMeasurement para que utilice la API sendBeacon de los navegadores
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '232'
ht-degree: 100%

---

# useBeacon

La mayoría de los exploradores modernos incluyen el método nativo `navigator.sendBeacon()`. Envía asincrónicamente una pequeña cantidad de datos a través de HTTP a un servidor web. AppMeasurement puede utilizar el método `navigator.sendBeacon()` si la variable `useBeacon` está habilitada. Resulta útil para los vínculos de salida y otras situaciones en las que desea enviar información antes de que se descargue la página.

Si `useBeacon` está activada, la siguiente visita enviada a Adobe utiliza el método del explorador `navigator.sendBeacon()` en lugar de una solicitud de imagen estándar `GET`. Esta variable se aplica tanto a solicitudes [`s.t()`](../functions/t-method.md) como a solicitudes de imagen [`s.tl()`](../functions/tl-method.md). Requiere AppMeasurement 2.17.0 o superior.

>[!TIP]
>
>AppMeasurement habilita automáticamente `useBeacon` para las solicitudes de imagen de vínculo de salida.

La variable `useBeacon` se omite cuando el visitante utiliza un explorador que no admite `navigator.sendBeacon()`. El uso de esta variable requiere AppMeasurement 2.16.0 o superior.

## Uso de la señalización mediante etiquetas en Adobe Experience Platform

No hay ningún campo específico en la IU de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.useBeacon en el editor de código personalizado de AppMeasurement y 

La variable `s.useBeacon` es un booleano que determina si AppMeasurement utiliza el método `navigator.sendBeacon()` del explorador. Su valor predeterminado es `false`. Establezca esta variable como `true` antes de llamar a una función de seguimiento si desea utilizar la naturaleza asincrónica de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Después de ejecutar una llamada de seguimiento, esta variable se restablece a `false`. Si la implementación envía varias solicitudes de imagen en la misma carga de página (como aplicaciones de una sola página), establezca esta variable como `true` antes de cada llamada de seguimiento.
