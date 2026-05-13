---
title: trackOffline
description: Habilite o deshabilite el seguimiento sin conexión, que cambia la forma en que AppMeasurement recopila datos.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xAeUI6N625MJfnAWWO53NkBe4IKxI-i703vHHoxpuzg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 89%

---

# trackOffline

El seguimiento sin conexión es una forma opcional de recopilar datos en Adobe Analytics. Si un visitante se desconecta de Internet pero continúa explorando el sitio, las visitas se almacenan en una cola sin conexión hasta que el dispositivo se vuelva a conectar a Internet. El seguimiento sin conexión se utiliza principalmente para aplicaciones móviles.

La variable `trackOffline` determina si desea utilizar el seguimiento sin conexión en la implementación.

>[!WARNING]
>
>Debe configurar el grupo de informes para que acepte visitas con marca de tiempo antes de habilitar esta variable. Si un grupo de informes no acepta visitas con marca de tiempo y esta variable está habilitada, los datos se pierden y no se pueden recuperar.

Cuando está habilitada, AppMeasurement utiliza el siguiente proceso para enviar datos a Adobe:

* Al compilar una solicitud de imagen, se incluye un parámetro de cadena de consulta de marca de tiempo.
* Si el dispositivo no puede acceder a los servidores de recopilación de datos de Adobe, la visita se almacena localmente en el dispositivo.
* Durante cada visita posterior, AppMeasurement intenta enviar una solicitud de imagen a Adobe.
   * Si no puede acceder a los servidores de recopilación de datos de Adobe, la visita se agrega a la cola del dispositivo.
   * Si puede acceder a los servidores de recopilación de datos de Adobe, se envían la visita y la cola de visitas mientras el dispositivo estaba sin conexión.

## Seguimiento sin conexión mediante Web SDK

Web SDK no admite el seguimiento sin conexión.

## Seguimiento sin conexión mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.trackOffline en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.trackOffline` es un booleano que habilita o deshabilita el seguimiento sin conexión. Su valor predeterminado es `false`. Establezca este valor como `true` si desea habilitar el seguimiento sin conexión.

```js
s.trackOffline = true;
```
