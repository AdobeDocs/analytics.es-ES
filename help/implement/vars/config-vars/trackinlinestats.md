---
title: trackInlineStats
description: Habilite o deshabilite Activity Map en la implementación.
keywords: desactivar activity map
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 78%

---

# trackInlineStats

Activity Map es una función de Adobe Analytics que recopila datos sobre dónde y en qué hacen clic los visitantes. Puede ver estos datos en los informes de Analytics o mediante una superposición de extensión de explorador. Active esta variable si desea utilizar las funciones de Activity Map.

Cuando se habilita, AppMeasurement recopila información sobre el vínculo y envía esos datos en la siguiente solicitud de imagen. La información de cada clic se almacena en una cookie etiquetada `s_sq`.

## Activity Map con el SDK web

El SDK web aún no admite la recopilación de datos de Activity Map.

## Habilitar Clickmap mediante la extensión de Adobe Analytics

[!UICONTROL Habilitar ClickMap] es una casilla de verificación en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Habilitar ClickMap].

Haga clic en la casilla de verificación para habilitar el seguimiento de Activity Map.

## s.trackInlineStats en AppMeasurement y el editor de código personalizado de la extensión de Analytics

`s.trackInlineStats` es un booleano que habilita o deshabilita el seguimiento de Activity Map. Su valor predeterminado es `false`. Establezca este valor como `true` si desea habilitar la recopilación de datos de Activity Map.

```js
s.trackInlineStats = true;
```
