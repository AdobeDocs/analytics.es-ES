---
title: trackInlineStats
description: Habilite o deshabilite Activity Map en la implementación.
keywords: desactivar activity map
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '192'
ht-degree: 100%

---

# trackInlineStats

Activity Map es una función de Adobe Analytics que recopila datos sobre dónde y en qué hacen clic los visitantes. Puede ver estos datos en los informes de Analytics o mediante una superposición de extensión de explorador. Active esta variable si desea utilizar las funciones de Activity Map.

Cuando se habilita, AppMeasurement recopila información sobre el vínculo y envía esos datos en la siguiente solicitud de imagen. La información de cada clic se almacena en una cookie etiquetada `s_sq`.

## Habilitar Clickmap en Adobe Experience Platform Launch

[!UICONTROL Habilitar ClickMap] es una casilla de verificación en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Habilitar ClickMap].

Haga clic en la casilla de verificación para habilitar el seguimiento de Activity Map.

## s.trackInlineStats en el editor de código personalizado de AppMeasurement y Launch

`s.trackInlineStats` es un booleano que habilita o deshabilita el seguimiento de Activity Map. Su valor predeterminado es `false`. Establezca este valor como `true` si desea habilitar la recopilación de datos de Activity Map.

```js
s.trackInlineStats = true;
```
