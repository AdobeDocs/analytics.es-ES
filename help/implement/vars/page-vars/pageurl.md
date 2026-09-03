---
title: pageURL
description: Omitir la dirección URL de la página registrada automáticamente en el sitio.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 84%

---

# pageURL

AppMeasurement registra automáticamente la dirección URL de la página en cada visita. Si desea omitir la dirección URL de la página registrada automáticamente por AppMeasurement, puede utilizar esta variable. No es necesario configurar esta variable en la mayoría de los casos.

>[!NOTE]
>
>Esta variable no es una dimensión disponible en Analysis Workspace. Solo está disponible en Data Warehouse y en Data Feeds. Además, los servidores de recopilación de datos de Adobe eliminan esta dimensión de todas las solicitudes de imagen de [seguimiento de vínculos](/help/implement/vars/functions/tl-method.md). Si desea utilizar la dirección URL de la página como dimensión en Analysis Workspace o desea tener esta dimensión en las visitas de seguimiento de vínculos, considere pasar la variable `pageURL` a una [eVar](evar.md) en cada visita.

## Dirección URL de la página mediante Web SDK

La dirección URL de la página está asignada a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` o `data.__adobe.analytics.g`

## Dirección URL de la página con la extensión Adobe Analytics

La extensión de Analytics en la recopilación de datos de Adobe Experience Platform rellena automáticamente la dirección URL de la página. Sin embargo, puede establecer la anulación de la dirección URL de la página al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña **[!UICONTROL Reglas]** y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En **[!UICONTROL Acciones]**, haga clic en una acción existente de **[!UICONTROL Adobe Analytics: Establecer variables]** o haga clic en el icono “+”.
5. Establezca la lista desplegable **[!UICONTROL Extensión]** en Adobe Analytics y el **[!UICONTROL tipo de acción]** en **[!UICONTROL Establecer variables]**.
6. Busque la sección **[!UICONTROL Dirección URL de la página]**.

Puede establecer la dirección URL de la página en cualquier valor de cadena.

## s.pageURL en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.pageURL` es una cadena que contiene la dirección URL de la página. AppMeasurement registra automáticamente esta variable, aunque puede anular su valor si lo desea.

```js
s.pageURL = "https://example.com";
```

Si desea utilizar la dirección URL de la página como dimensión en los informes, pruebe a utilizar lo siguiente en la implementación:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
