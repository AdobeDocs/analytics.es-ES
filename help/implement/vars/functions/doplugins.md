---
title: doPlugins
description: Configure la lógica justo antes de compilar una visita y enviarla a Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 66%

---

# doPlugins

La variable `doPlugins` actúa como una “última llamada” para establecer los valores en la implementación. Si [`usePlugins`](../config-vars/useplugins.md) está habilitada, se ejecuta automáticamente justo antes de que se compile y envíe a Adobe cualquier tipo de solicitud de imagen, lo que incluye:

* Todas las llamadas a la vista de página ([`t()`](t-method.md))
* Todas las llamadas de seguimiento de vínculos ([`tl()`](tl-method.md)), incluidos los vínculos de descarga automática y los vínculos de salida

Utilice la variable `doPlugins` para llamar al código del complemento y establecer los valores de la variable final justo antes de compilar una solicitud de imagen y enviarla a Adobe.

## Utilice el código de devolución de llamada Activado antes del envío de evento con la extensión SDK para web

En lugar de `doPlugins`, el SDK web utiliza `onBeforeEventSend` con una funcionalidad similar.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Recopilación de datos], haga clic en **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]** botón.
1. Coloque el código deseado en el editor.

## Uso `onBeforeEventSend` implementación manual del SDK web

En lugar de `doPlugins`, el SDK web utiliza `onBeforeEventSend` con una funcionalidad similar. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

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
