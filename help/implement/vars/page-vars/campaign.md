---
title: campaign
description: Rellene la dimensión “Código de seguimiento”.
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/4OF7xoZs8bLS4UW8wfJYHqSyc-gNVLAfPs5j3NwZCcM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 74%

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
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
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
