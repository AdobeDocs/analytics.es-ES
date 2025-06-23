---
title: campaign
description: Rellene la dimensión “Código de seguimiento”.
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 67%

---

# campaign

La variable `campaign` está dedicada a recopilar códigos de seguimiento en el sitio. En versiones anteriores de Adobe Analytics, se le aplicaba un tratamiento especial en el que podía utilizarse como desglose de la mayoría de las dimensiones. En la versión actual de Adobe Analytics, actúa igual que una eVar.

Esta variable rellena la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). Normalmente obtiene su valor de una cadena de consulta utilizando el método de utilidad [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md). Sin embargo, su organización determina exactamente cómo configurar esta variable.

## Campaña mediante Web SDK

Campaign se asigna a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` o `data.__adobe.analytics.v0`

## Campaña con la extensión de Adobe Analytics

Puede establecer la campaña durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Campaña].

Puede establecer la campaña como un valor o un parámetro de cadena de consulta.

## s.campaign en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.campaign` es una cadena que generalmente contiene un código de seguimiento utilizado en los esfuerzos de marketing. Su longitud máxima es de 255 bytes; los valores superiores a 255 bytes se truncan automáticamente cuando se envían a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
