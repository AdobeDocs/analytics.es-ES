---
title: trackOffline
description: Habilite o deshabilite el seguimiento sin conexión, que cambia la forma en que AppMeasurement recopila datos.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackOffline

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La `trackOffline` variable determina si desea utilizar el seguimiento sin conexión en la implementación.

> [!IMPORTANT] Debe configurar el grupo de informes para que acepte visitas con marca de hora antes de habilitar esta variable. Si un grupo de informes no acepta visitas con marca de hora y esta variable está habilitada, los datos se pierden y no se pueden recuperar.

Cuando está habilitada, AppMeasurement utiliza el siguiente proceso para enviar datos a Adobe:

* Al compilar una solicitud de imagen, se incluye un parámetro de cadena de consulta de marca de hora.
* Si el dispositivo no puede acceder a los servidores de recopilación de datos de Adobe, la visita se almacena localmente en el dispositivo.
* Durante cada visita posterior, AppMeasurement intenta enviar una solicitud de imagen a Adobe.
   * Si no puede acceder a los servidores de recopilación de datos de Adobe, la visita se agrega a la cola del dispositivo.
   * Si puede llegar a los servidores de recopilación de datos de Adobe, se envían la visita y la cola de visitas mientras el dispositivo estaba sin conexión.

## Seguimiento sin conexión en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.trackOffline en el editor de código personalizado AppMeasurement e Launch

La `s.trackOffline` variable es un booleano que habilita o deshabilita el seguimiento sin conexión. Its default value is `false`. Establezca este valor en `true` si desea habilitar el seguimiento sin conexión.

```js
s.trackOffline = true;
```
