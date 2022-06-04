---
title: trackOffline
description: Habilite o deshabilite el seguimiento sin conexión, que cambia la forma en que AppMeasurement recopila datos.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

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

## Seguimiento sin conexión con etiquetas en Adobe Experience Platform

No hay ningún campo específico en la IU de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.trackOffline en el editor de código personalizado de AppMeasurement y 

La variable `s.trackOffline` es un booleano que habilita o deshabilita el seguimiento sin conexión. Su valor predeterminado es `false`. Establezca este valor como `true` si desea habilitar el seguimiento sin conexión.

```js
s.trackOffline = true;
```
