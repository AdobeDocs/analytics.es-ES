---
title: doPlugins
description: Configure la lógica justo antes de compilar una visita y enviarla a Adobe.
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
TQID: https://experienceleague.adobe.com/T-AyesoP2IMk3J-ftdnR-o48HqTmoRsAYtaIgn9cc1Q
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
source-wordcount: 326
ht-degree: 61%

---

# doPlugins

La variable `doPlugins` actúa como una “última llamada” para establecer los valores en la implementación. Es el lugar ideal para hacer llamadas a [métodos de complemento](../plugins/impl-plugins.md) y establecer las variables deseadas antes de enviar una solicitud de imagen. Si [`usePlugins`](../config-vars/useplugins.md) está habilitada, se ejecuta automáticamente justo antes de que se compile y envíe a Adobe cualquier tipo de solicitud de imagen, lo que incluye:

* Todas las llamadas a la vista de página ([`t()`](t-method.md))
* Todas las llamadas de seguimiento de vínculos ([`tl()`](tl-method.md)), incluidos los vínculos de descarga automática y los vínculos de salida

Utilice la variable `doPlugins` para llamar al código del complemento y establecer los valores de la variable final justo antes de compilar una solicitud de imagen y enviarla a Adobe.

## Utilice el código de devolución de llamada Activado antes del envío de evento con la extensión Web SDK

En lugar de `doPlugins`, Web SDK usa `onBeforeEventSend` con una funcionalidad similar.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en el botón **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]**.
1. Coloque el código deseado en el editor.

## Usar `onBeforeEventSend` para implementar manualmente Web SDK

En lugar de `doPlugins`, Web SDK usa `onBeforeEventSend` con una funcionalidad similar. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación de Web SDK para obtener más información.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Complementos con la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.doPlugins en el editor de código personalizado de AppMeasurement y

Establezca la variable `s.doPlugins` como una función que contenga el código deseado. La función se ejecuta automáticamente cuando realiza una llamada de seguimiento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Establezca una función en la variable `doPlugins` solo una vez en la implementación. Si establece la variable `doPlugins` más de una vez, solo se utilizará el código más reciente.

## Ejemplos

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Las versiones anteriores de AppMeasurement tenían un código ligeramente diferente `doPlugins()`. Adobe recomienda utilizar el formato anterior.
