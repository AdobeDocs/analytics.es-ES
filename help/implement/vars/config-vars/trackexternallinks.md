---
title: trackExternalLinks
description: Habilite o deshabilite el seguimiento automático de vínculos de salida.
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jNToCI8XjnbDNdTj6gwveVIWt3Ehue6Hp1HWM789UeI
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
source-wordcount: 340
ht-degree: 59%

---

# trackExternalLinks

Adobe ofrece la capacidad de rastrear vínculos salientes sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de salida. Habilite esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de salida.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo en el que se haga clic con los valores en [`linkInternalFilters`](linkinternalfilters.md) y [`linkExternalFilters`](linkexternalfilters.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de salida.

## Habilite o deshabilite la recopilación de clics mediante la extensión Web SDK

Utilice la casilla de verificación [!UICONTROL Habilitar la recopilación de datos con clic] al configurar Web SDK. Esta casilla de verificación gestiona los vínculos de salida y de descarga.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en la casilla de verificación **[!UICONTROL Habilitar la recopilación de datos con clic]**.

## Habilitar o deshabilitar la recopilación de clics manualmente al implementar Web SDK

Configure SDK usando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). El campo es un booleano que determina si los datos asociados con los clics en vínculos se recopilan automáticamente. Su valor predeterminado es `true`. Establezca este valor en `false` si desea deshabilitar el seguimiento automático de vínculos. Esta configuración administra el seguimiento automático de vínculos tanto para los vínculos de descarga como de salida.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Seguimiento de vínculos de salida con la extensión Adobe Analytics

Rastrear vínculos de salida es una casilla de verificación bajo el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de salida].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de salida.

## s.trackExternalLinks en AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.trackExternalLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de salida. Si no desea rastrear los vínculos de salida o prefiere llamar manualmente al método `tl()` para rastrear los vínculos de salida, debe establecer esta variable como `false`.

```js
s.trackExternalLinks = true;
```
