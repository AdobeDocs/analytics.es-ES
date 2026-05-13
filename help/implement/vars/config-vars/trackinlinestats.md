---
title: trackInlineStats
description: (Retirado) Habilite o deshabilite ClickMap en la implementación.
keywords: deshabilitar clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: https://experienceleague.adobe.com/K6rwl-ZECfoMLfC0Z25PPq2jV1FBo0cTsl1YfDeNpBQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

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
