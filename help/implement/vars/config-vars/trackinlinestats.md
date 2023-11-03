---
title: trackInlineStats
description: Habilite o deshabilite el ClickMap en la implementación.
keywords: deshabilitar clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 31%

---

# trackInlineStats

>[!IMPORTANT]
>
>Esta variable está retirada. Consulte [Habilitar Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) en su lugar.

ClickMap es una función retirada de Adobe Analytics que recopila datos sobre dónde y en qué hacen clic los visitantes. La función se ha reemplazado por [Activity Map](/help/analyze/activity-map/activity-map.md).

Cuando se habilita, AppMeasurement recopila información sobre el vínculo y envía esos datos en la siguiente solicitud de imagen. La información de cada clic se almacena en una cookie denominada `s_sq`.

## Habilitar el ClickMap con la extensión de Adobe Analytics

[!UICONTROL Habilitar ClickMap] es una casilla de verificación debajo de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el [!UICONTROL Seguimiento de vínculos] acordeón, que revela el [!UICONTROL Habilitar ClickMap] casilla de verificación

>[!NOTE]
>
>Esta casilla de verificación es diferente de la [!UICONTROL Usar Activity Map] , que se encuentra en la casilla de verificación [!UICONTROL Administración de biblioteca] acordeón.

## s.trackInlineStats en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.trackInlineStats` es un booleano que habilita o deshabilita el seguimiento de ClickMap. Dado que se ha eliminado la función, el Adobe no recomienda configurar esta variable. Su valor predeterminado es `false`.

```js
s.trackInlineStats = false;
```
