---
title: trackInlineStats
description: (Retirado) Habilite o deshabilite ClickMap en la implementación.
keywords: deshabilitar clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---

# trackInlineStats

>[!IMPORTANT]
>
>Esta variable desaparece y ya no se utiliza.

ClickMap es una función retirada de Adobe Analytics que recopila datos sobre dónde y en qué hacen clic los visitantes. La característica se reemplazó con [Activity Map](/help/analyze/activity-map/overview.md).

Cuando se habilita, AppMeasurement recopila información sobre el vínculo y envía esos datos en la siguiente solicitud de imagen. La información de cada clic se almacena en una cookie denominada `s_sq`.

## Habilitar ClickMap con la extensión de Adobe Analytics

[!UICONTROL Habilitar ClickMap] es una casilla de verificación en el acordeón [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Habilitar ClickMap].

>[!NOTE]
>
>Esta casilla de verificación es diferente de la casilla de verificación [!UICONTROL Usar Activity Map], que se encuentra en el acordeón [!UICONTROL Administración de biblioteca].

## s.trackInlineStats en AppMeasurement y el editor de código personalizado de la extensión de Analytics

`s.trackInlineStats` es un booleano que habilita o deshabilita el seguimiento de ClickMap. Dado que la función se ha eliminado, Adobe no recomienda configurar esta variable. Su valor predeterminado es `false`.

```js
s.trackInlineStats = false;
```
